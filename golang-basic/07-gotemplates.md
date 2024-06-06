### Lecture Notes

* ***What's a Template?***: Get to know what templates are and why they're useful when you're building your app.
* ***How to Write in Template Language***: Learn the simple rules for writing templates in Go so you can start making your own.
* ***Adding Your Information to a Template***: Find out how to put your own info into templates and change output depending on what you need.
* ***Extra Template Tricks***: Boost your templates with special functions and learn about the Sprig library, which gives you even more cool things you can do.

Presentation: https://docs.google.com/presentation/d/1bbJkLodVaL3bOqHfacmhZlG6cOYUNSfx/edit?usp=drive_link&ouid=107330001931294770933&rtpof=true&sd=true

### Something to read

https://pkg.go.dev/text/template
https://golangforall.com/en/post/templates.html
https://blog.gopheracademy.com/advent-2017/using-go-templates/
https://developer.hashicorp.com/nomad/tutorials/templates/go-template-syntax
https://www.youtube.com/watch?v=k5wJv4XO7a0

### Task: Change the News Output Format
1. All logic must be implemented using go templates (except for sorting). There should be one main template.
2. There should be a common header with information about which filters are applied and the number of news items.
3. If there are no news items, there should be a message indicating this.
4. News items must be sorted by date (add a parameter for sorting order DESC/ASC).
5. The date for all news items must be in a consistent format and in the user's timezone.
6. It should also be possible to sort by news sources (e.g., BBC, ABC). In this case, there will be news blocks, and each block will have its own header. The header should state the news source and the number of news items. In this case, do not display the name of the news source next to each news item (if there is no sorting by sources, then display the name of the source next to each news item).
7. Bonus: If there is Keyword Filtering, highlight the words that matched the filter (for example, ~~text~~), and try to implement this by adding a custom Template function.
