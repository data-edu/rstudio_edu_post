Learning More About What Readers Need (Working Title)
================
Ryan Estrellado and Joshua Rosenberg
7/9/2020

When we wrote Data Science for Education Using R, we knew it would be
easy to assume new learners would have more prior knowledge about R than
they actually did. We knew this intuitively because, as more experienced
R users, we only vaguely associate feelings of triumph and frustration
with the memory of running that first chunk of R code. The details of
where we got stuck in our learning are harder to recollect. Afterall, as
new R learners we were, as our co-author [Jesse puts
it](https://twitter.com/kierisi/status/1100227355543359488?s=20), “going
from using our computers for Netflix to using them for programming and
data science.”

Over time, we trade in fresh memories of our learning pain points for
experience and ease of use. That led to a design problem we had to solve
while writing Data Science in Education Using R: How do we write with
empathy for new learners when our own memories about learning R have
gotten foggier?. There are all kinds of ways to do this, like
“listening” on social media, interviewing community members, and
regularly trying to learn new things ourselves.

Open source materials are another opportunity to learn about what our
audience needs. [Open source educational resources, software, and
science make R code available to readers to encourage collaboration and
accountability](https://rviews.rstudio.com/2020/07/01/open-source-authorship-of-data-science-in-education-using-r/).
But can open source writing also help us check our biases about what
learners need by including the learners themselves in the development of
materials?

When we data scientists share their writing and code through sites like
GitHub and Kaggle, that sharing comes with an unspoken invitation to
communicate with the authors. Most of the time, that communication is
about improving code. When the open source resource is designed to teach
someone something new, the communication can also be about improving the
learning experience.

Consider a scenario where a classroom teacher asks their students to
complete worksheets, an example of closed source education materials.
Not only do worksheets hide the underlying thinking behind their
creation, they also invite compliance more than they invite any
conversation about what the learner needs.

Let’s look at an example from our book. In chapter 8, we use a created a
visualization to explore scores from student classwork assignments:

``` r
# Scatterplot of continuous variable
classwork_df %>%
  ggplot(aes(x = reorder(classwork_number, -score, median),
             y = score,
             fill = classwork_number)) +
  geom_boxplot() +
  labs(title = "Distribution of Classwork Scores",
       x = "Classwork",
       y = "Scores") +
  scale_fill_dataedu() +
  theme_dataedu() +
  theme(
    # removes legend
    legend.position = "none",
    # angles the x axis labels
    axis.text.x = element_text(angle = 45, hjust = 1)
    )
```

![](rstudio_edu_post_files/figure-gfm/plot-1.png)<!-- -->

By making the code for this plot
[available](https://github.com/data-edu/rstudio_edu_post), we invite
readers to tell us where we could have done more to scaffold the lesson.
For example, a reader might tell us they need a better explanation of
how `reorder()` is used to arrange the boxplots by median scores.