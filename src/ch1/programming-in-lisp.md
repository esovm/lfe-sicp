## Programming in Lisp

We need an appropriate language for describing processes, and we will use for this purpose the programming language Lisp. Just as our everyday thoughts are usually expressed in our natural language (such as English, French, or Japanese), and descriptions of quantitative phenomena are expressed with mathematical notations, our procedural thoughts will be expressed in Lisp. Lisp was invented in the late 1950s as a formalism for reasoning about the use of certain kinds of logical expressions, called recursion equations, as a model for computation. The language was conceived by John McCarthy and is based on his paper "[Recursive Functions of Symbolic Expressions and Their Computation by Machine](http://www-formal.stanford.edu/jmc/recursive.pdf)" (McCarthy 1960).

Despite its inception as a mathematical formalism, Lisp is a practical programming language. A Lisp interpreter is a machine that carries out processes described in the Lisp language. The first Lisp interpreter was implemented by McCarthy with the help of colleagues and students in the Artificial Intelligence Group of the MIT Research Laboratory of Electronics and in the MIT Computation Center.[^1] Lisp, whose name is an acronym for LISt Processing, was designed to provide symbol-manipulating capabilities for attacking programming problems such as the symbolic differentiation and integration of algebraic expressions. It included for this purpose new data objects known as atoms and lists, which most strikingly set it apart from all other languages of the period.

Lisp was not the product of a concerted design effort. Instead, it evolved informally in an experimental manner in response to users' needs and to pragmatic implementation considerations. Lisp's informal evolution has continued through the years, and the community of Lisp users has traditionally resisted attempts to promulgate any "official" definition of the language. This evolution, together with the flexibility and elegance of the initial conception, has enabled Lisp, which is the second oldest language in widespread use today (only Fortran is older), to continually adapt to encompass the most modern ideas about program design. Thus, Lisp is by now a family of dialects, which, while sharing most of the original features, may differ from one another in significant ways. The dialect of Lisp used in the first two editions of this book was Scheme.[^2] The dialect used in this edition of the book is Lisp Flavored Erlang.[^3]

Because of its experimental character and its emphasis on symbol manipulation, Lisp was at first very inefficient for numerical computations, at least in comparison with Fortran. Over the years, however, Lisp compilers have been developed that translate programs into machine code that can perform numerical computations reasonably efficiently. And for special applications, Lisp has been used with great effectiveness.[^4] Although Lisp has not yet overcome its old reputation as hopelessly inefficient, Lisp is now used in many applications where efficiency is not the central concern. For example, Lisp has become a language of choice for operating-system shell languages and for extension languages for editors and computer-aided design systems.

If Lisp is not a mainstream language, why are we using it as the framework for our discussion of programming? Because the language possesses unique features that make it an excellent medium for studying important programming constructs and data structures and for relating them to the linguistic features that support them. The most significant of these features is the fact that Lisp descriptions of processes, called functions, can themselves be represented and manipulated as Lisp data. The importance of this is that there are powerful program-design techniques that rely on the ability to blur the traditional distinction between "passive" data and "active" processes. As we shall discover, Lisp's flexibility in handling functions as data makes it one of the most convenient languages in existence for exploring these techniques. The ability to represent functions as data also makes Lisp an excellent language for writing programs that must manipulate other programs as data, such as the interpreters and compilers that support computer languages. Above and beyond these considerations, programming in Lisp is great fun.

----

[^1]: The [Lisp 1 Programmer's Manual](http://www.softwarepreservation.org/projects/LISP/book/LISP%20I%20Programmers%20Manual.pdf) appeared in 1960, and the [Lisp 1.5 Programmer's Manual](http://www.softwarepreservation.org/projects/LISP/book/LISP%201.5%20Programmers%20Manual.pdf) (McCarthy 1965) was published in 1962. The [early history of Lisp](http://www-formal.stanford.edu/jmc/history/lisp/lisp.html) is described in McCarthy 1978. 

[^2]: The two dialects in which most major Lisp programs of the 1970s were written are [MacLisp](https://en.wikipedia.org/wiki/Maclisp) (Moon 1978; Pitman 1983), developed at the [MIT Project MAC](https://en.wikipedia.org/wiki/MIT_Computer_Science_and_Artificial_Intelligence_Laboratory#Project_MAC), and [Interlisp](https://en.wikipedia.org/wiki/Interlisp) (Teitelman 1974), developed at Bolt Beranek and Newman Inc. and the Xerox Palo Alto Research Center. [Portable Standard Lisp](https://en.wikipedia.org/wiki/Portable_Standard_Lisp) (Hearn 1969; Griss 1981) was a Lisp dialect designed to be easily portable between different machines. MacLisp spawned a number of subdialects, such as [Franz Lisp](https://en.wikipedia.org/wiki/Franz_Lisp), which was developed at the University of California at Berkeley, and [Zetalisp](https://en.wikipedia.org/w/index.php?title=ZetaLisp&redirect=no) (Moon 1981), which was based on a special-purpose processor designed at the MIT Artificial Intelligence Laboratory to run Lisp very efficiently. The Lisp dialect used in the first two editions of this book, called [Scheme](https://en.wikipedia.org/wiki/Scheme_%28programming_language%29) (Steele 1975), was invented in 1975 by Guy Lewis Steele Jr. and Gerald Jay Sussman of the MIT Artificial Intelligence Laboratory and later reimplemented for instructional use at MIT. Scheme became an IEEE standard in 1990 (IEEE 1990). The [Common Lisp](https://en.wikipedia.org/wiki/Common_Lisp) dialect (Steele 1982, Steele 1990) was developed by the Lisp community to combine features from the earlier Lisp dialects to make an industrial standard for Lisp. Common Lisp became an ANSI standard in 1994 (ANSI 1994). 

[^3]: [Lisp Flavored Erlang](https://en.wikipedia.org/wiki/LFE_%28programming_language%29), more commonly referred to as LFE, is a Common Lisp (and Scheme) inspired variant created to run on the [Erlang](https://en.wikipedia.org/wiki/Erlang_%28programming_language%29) BEAM (also known as the "Erlang virtual machine"). LFE was created by Robert Virding (second co-creator of the Erlang programming language, the first being Joe Armstrong) in late 2007 in the same spirit that Alan Perlis describes in the dedication of this book: fun. The first version was released in early 2008. It received steady development work over the course of the following four years, and then in 2012 and 2013 began to see an up-tick in community interest, contributions, and third-party libraries. By 2014, companies were starting to use it on projects and in 2015 start ups began selecting it as their platform of choice for distributed systems programming.

[^4]: One such special application was a breakthrough computation of scientific importance -- an integration of the motion of the Solar System that extended previous results by nearly two orders of magnitude, and demonstrated that the dynamics of the Solar System is chaotic. This computation was made possible by new integration algorithms, a special-purpose compiler, and a special-purpose computer all implemented with the aid of software tools written in Lisp (Abelson et al. 1992; Sussman and Wisdom 1992). 

