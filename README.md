# Reviews Site

## Module Resources

Opinions. You know the saying...everyone has one. And the Internet has made them easier to consume, or ignore.

Acquisitions, Inc. has many, many products from its years of, well, acquiring things. They have asked you to build a reviews site for some of their current products. The data gathered will help them gain insight into their customer base and the products they have come to enjoy...or enjoy less.

Acquisitions, Inc. requires:

- Development of a MVC Web Application that practices agile methodology, utilizes test driven design, and values clean code
- Appropriate use of Git and access to your application on GitHub
- Useful instructions in the form of a README.md file


## Materials

- [Dependency Injection](https://wecancodeit.github.io/java-slides/mvc/dependency-injection.html#/)
- [Dependency Injection (Moar!)](https://wecancodeit.github.io/java-slides/objects/dependency-injection/index.html#/)
- [Intro to MVC](https://wecancodeit.github.io/java-slides/mvc/intro-to-mvc.html#/)
- [Spring Boot](https://wecancodeit.github.io/java-slides/spring/spring-boot/index.html#/)
- [Thymeleaf](https://wecancodeit.github.io/java-slides/web/thymeleaf/index.html#/)
- [Thymeleaf Tutorial](http://www.thymeleaf.org/doc/tutorials/2.1/usingthymeleaf.html)

## Deliverables

- Create a Review class for the content of reviews. Its properties should include: id, title, imageUrl, reviewCategory (singular), content
- Create a ReviewRepository
  - It should have a constructor that houses a List of Reviews
  - should have a method to find all reviews
  - should have a method to find one review by id
- Create a ReviewsController class.
  - It should have a method mapped to a url outputs all reviews and allows the user to add a review via an HTML form
  - should have a method mapped to a url including an id parameter that outputs the details of a single review

## Thymeleaf Tips

### Iteration

We use `th:each` to iterate over collections in Thymeleaf. If I had a collection called `widgets` in my model, each of these having a `name` attribute, I would do the following to generate a `<div>` for each of these. `widget` is the name of my iteration variable, much like the for each loops you're familar with:

```HTML
<div th:each="widget: ${widgets}" th:text="${widget.name}" />
```

This would result in something like the following, given the names "fee", "fie", and "foe":

```HTML
<div>fee</div>
<div>fie</div>
<div>foe</div>
```

(See the [tutorial section on iteration](http://www.thymeleaf.org/doc/tutorials/2.1/usingthymeleaf.html#iteration).)

### Link URLs

Link urls have a special syntax in Thymeleaf, the `@` syntax: `@{...}`. If I had an object called `foo` in the model, with a `getId()` method, and wanted to create a query parameter with the id, I would reference it as follows:

```HTML
<a th:href="@{/things/${thing.id}}">link text</a>
```

This would result in the following being rendered, assuming that `thing.getId()` returns 42:

```HTML
<a href="/things/42">link text</a>
```

(See the [tutorial section on link urls](http://www.thymeleaf.org/doc/tutorials/2.1/usingthymeleaf.html#link-urls).)
