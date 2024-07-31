We now build a k8s extension using Operator concept, where we use Custom Resource Definition and controller-manager pod
which allow configuring/managing news feeds with a native k8s resource.
[Kubebuilder](https://book.kubebuilder.io/introduction.html) is a k8s operator framework which makes it easy.

### Description

#### `Feed`
The task is to bootstrap kubebuilder project and define a CRD which allows to create and manage news sources (feeds).

You need to handle all CRUD actions on your Custom Resource:
* if a user creates CR — it should create new sources in the news-aggregator;
* if a user updates CR - it should update corresponding source in the news-aggregator;
* if a user deletes CR - it should remove the source from the news-aggregator.

The Kubernetes Custom Resource need to have the following schema:
```yaml
apiVersion: teamdev.com/v1
kind: Feed
metadata:
  # name of the crd
  name: <string>
  # the resource should be namespaced
  namespace: <string>
spec:
  # name of the news source
  name: <string>
  # link to the news source
  link: <string>
status:
  # you can come up with your own status fields, below is just an example
  conditions:
  - type: <enum> (Added, etc)
    # True or False
    # True, if the feed was successfully added to the news-aggregator
    # False, if the feed was not successfully added to the news-aggregator
    status: True/False
    # If status is False, the reason should be populated
    reason: REASON
    # If status is False, the message should be populated
    message: MESSAGE
    # A time when an object moves in this state
    lastUpdateTime: ""
```

#### `HotNews`
Define a CRD, which allows to create hot news based on available `Feeds` and current functionality of the news-aggregator.

```yaml
kind: HotNews
metadata:
  # name of the crd
  name: <string>
  # the resource should be namespaced
  namespace: <string>
spec:
    # a list of keywords, must be always required
	keywords: <list>
	# start date, can be empty
	dateStart: <string>
	# end date, can be empty
	dateEnd: <string>
    # all feed names in the current namespace, if empty — will watch ALL available feeds.
	feeds: <list>
	# Available sections of feeds from `feed-group-source` ConfigMap
	feedGroups: <list>
	# configure how status will show the summary of observed hot new
	# more fields can be added if needed
	summaryConfig:
		titlesCount: 10
status:
    # count of articles by the criteria
	articlesCount: <number>
	# a link to the news-aggregator HTTPs server to get all news by the criteria in JSON format
	newsLink: <string>
	# first  "spec.summaryConfig.titlesCount" article titles, sorted by feed name
	articlesTitles: <list>
---
kind: ConfigMap
name: feed-group-source
data:
    # key is the name of the feed group, value is the comma-separated list of feed names
	sport: "usa-sports,nba" 
	westMedias: "bbc,nbc,washingtontimes,nytimes"
```

You will have to support the next scenarios:
1. Update of any feeds defined in the `HotNews`, should trigger `HotNews` reconciler.
2. Any changes in the `feed-group-source` ConfigMap, should trigger `HotNews` reconciler.
