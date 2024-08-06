### Description
You will have to implement two webhooks:
1. ValidatingWebhook
2. MutatingWebhook

#### Feed CRD
Validation rules:
```yaml
apiVersion: teamdev.com/v1
kind: Feed
spec:
  # should be unique in a namespace
  # should not be more than 20 symbols
  # can not be empty
  name: <string>
  # should be unique in a namespace
  # should be validated by URL pattern
  # can not be empty
  link: <string>
```

#### HostNews CRD
```yaml
apiVersion: teamdev.com/v1
kind: HotNews
spec:
    # must be always required, can not be empty
	keywords: <list>
	# optional
	# should be always before dateEnd
	# should be validate if that's a date in a correct format
	dateStart: <string>
	# optional
	# should be always after datStart
	# should be validate if that's a date in a correct format
	dateEnd: <string>
    # optional
	feeds: <list>
	# optional
	# should verify if the groups exist in Config Map with feed-group-source
	feedGroups: <list>
    # optional
	summaryConfig:
	    # default value should 10
		titlesCount: 10
```

#### CM `feed-group-source`
```yaml
kind: ConfigMap
name: feed-group-source
data:
    # optional
    # should validate if below feeds exists
	sport: "usa-sports,nba" 
	# optional
	# should validate if below feeds exists
	westMedias: "bbc,nbc,washingtontimes,nytimes"
```