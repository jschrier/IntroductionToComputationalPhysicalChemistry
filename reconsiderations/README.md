# Reconsiderations

Late in his life, at the age of 72, [St. Augustine of Hippo](https://en.wikipedia.org/wiki/Augustine_of_Hippo) undertook to review his voluminous writings, commenting on them and how his opinions had changed.  
His resulting manuscript, the [Retractiones](http://augnet.org/en/works-of-augustine/writings-of-augustine/2148-the-retractions/) (best translated as *Reconsiderations*), comprises details about the circumstances of the work, corrections of errors, and areas where he wanted to revise (in Latin, *reprehensiones*) or explain further (in Latin, *defensiones*).

In the years since publishing *Introduction to Computational Physical Chemistry*, I too have continued to study how students learn the material and think of the best way to teach the material.
While the errors are already described in the [Errata](https://github.com/jschrier/IntroductionToComputationalPhysicalChemistry/blob/master/errata.md), these reconsiderations are to discuss certain *reprehensiones* and *defensiones* of the Mathematica implementation of the material.  

My main reconsideration is that I have come to think that a [functional programming](https://en.wikipedia.org/wiki/Functional_programming) approach is both possible and optimal for the typical physical chemistry undergraduate student who is learning programming for the first time.  
This may seem odd, as introductory coomputer science coursework typically teaches [procedural programming](https://en.wikipedia.org/wiki/Procedural_programming) first, with functional programming considered a somewhat esoteric topic for more advanced students.  
The text was written with that standard wisdom in mind, following a very procedural style of programing, of the kind that would be familiar to the typical FORTRAN, MATLAB, C, or introductory Python student.  
However, what I have found is that the many advantages of functional programming---in particularly a preference for [pure functions](https://en.wikipedia.org/wiki/Procedural_programming) and avoiding index counting by using Map operations---is often more natural for sutdents, as it more closely corresponds to the mathematical ideas that they have been trained in. 

Thus, in these reconsiderations I will examine how the content would change to introduce a more functional style to the implementation.  