---
layout: essay
type: essay
title: "The 'Goldilocks problem' of programming languages"
# All dates must be YYYY-MM-DD format!
date: 2025-01-22
published: true
labels:
  - JavaScript/TypeScript
  - Programming Languages
---

<img width="700px" class="rounded float-start pe-4" src="../img/essays-img/programming-languages.png">

Every programmer has a preferred coding language. For some, it is the first language they learned; for others, it is the language they are currently using for work, school, or some personal project. There are those who prefer C++, Python, or JavaScript, and even mad geniuses that enjoy assembly. 

Personally, I prefer **Python** because it is both the first language I learned and a language with a flush collection of libraries to implement machine learning and artifical intelligence. Although I am a Python enthuasiast, I do lament the lack of braces and understand the argument of the language feeling _loose_ in terms of typecasting variables and the lengthy compilation process.

Compared to Python, I found Javascript (a language that I recently picked up as of writing), to feel very familiar---like Python but with braces! Then, I began to wonder how the current programming languages I know (C, C++, Python, JavaScript, TypeScript) stack up against each other and which one is logically "just right" without personal biases. This is how my idea of the **Goldilocks Problem** for programming languages came to be.


## Too rigid!

First and foremost, I consider C and C++ to be the most rigid of the languages I know, simply by the virtue of the language being low-level and working directly with memory and hardware. Whilst working with C and C++, I find myself maintaining a very methodical and precise mindset. Not only do I have to plan out most details of the program I intend to create but I have to recall all the required datatypes, how memory changes, and how to deal with unexpected errors thrown my way.

A fantastic example of this originates from an old college project of designing a [simple API from scratch](https://github.com/aar0m/cat-farm). This section demonstrates an Animal class alongside its possible methods, implemented using C++.

```cpp
class Animal : public Node {

protected:
	float weight;    /// The specified 'weight' (in pounds) of the Animal

public:
	Animal( float newWeight );   ///< Generates an Animal with a specified 'weight'
	Animal();                    ///< Generates an Animal with a random valid 'weight'

// Methods //
	static std::string_view getKingdom() noexcept;   ///< Returns 'kingdom' of Animal

	static bool validateWeight( float weight );      ///< Validates 'weight'
	virtual bool validate() const noexcept;          ///< Validates Animal 

	/// Prints information of Animal (Node properties, 'kingdom', Gender)
	virtual void dump() const noexcept;

	/// Generates a random 'weight' in pounds for an Animal
	static float generatePounds() noexcept;

	/// Makes the Animal speak!
	virtual std::string_view speak() const noexcept = 0;

	/// Gets the Name of the Animal
	virtual std::string_view getName() const noexcept = 0;

	/// Print a unique one-line string representing this object
	virtual void info() const noexcept;

	/// Generates a random Animal with random specifications
	static Animal* getRandomAnimal();
};
```

From this, we note the various types and sheer presence of keywords to describe object methods, datatypes, and even the class itself. Each item is specifically crafted with various types that are developed with heavy consideration of how this class will interact with other methods, classes, and functions! Such required insight and methodical planning, as well as the explicitly required declaration of types, makes C and C++ too rigid to be the "just right" programming language.


## Too flexible!

I have already iterated that Python feels the most loose and fast. Fantastic for creating scripts and using libraries but very easy to lose track of whitespaces, forget what datatypes are being used, and ensuring instructions execute where they need to be executed. For exmaple, examine the following excerpt from a function to get calories from my [weight tracker project](https://aar0m.github.io/projects/weight_tracker.html):

```python
def getCal():
    fr.prMethodHead("Calorie Logging Process Initiated")
    mealTypes = ["Breakfast", "Lunch", "Dinner", "Snack"]

    while True: 
        print("What type of food are you logging?")
        for i, mealType in enumerate(mealTypes):
            print(f"{i+1}. {mealType}")
        break

    possVal = f"[1 - {len(mealTypes)}]"
```

As shown, variables are simply instantiated without regard for types, while functions are called on elements with inferred types. Without explicti declarations, thes variables could be transformed and I would be none the wiser (until errors messages are thrown). On top of all this, there are no braces! Therefore, it can be concluded that Python, while great for programmers who want to quickly make scripts or work with libraries, feels too loose to be considered a programming language that is "just right". 


## TypeScript : just right!

Like Python, JavaScript and its ambiguous typing falls under the same pitfall as Python but with braces. As a newbie to JavaScript (as of writing), the language really did feel like a blend of Python and C/C++, for better or for worse. Being able to write code with braces and types made me feel like I was writing in C but being able to speedily write code emphasized the Pythonic aspect of JavaScript. Unfortunately, I still felt JavaScript to be too loose to be considered "just right."

Enter Typescript. Flexible due to inheriting JavaScript conventions, yet explicit and distinct enough to emulate the typing behavior of C/C++. This was not totally apparent at first but through an athletic software engineering practices---a workflow I find enjoyable due to its realistic pressures, fast pace, and the rewarding feeling when succesfully prepared for/completed---I noticed that TypeScript may be the answer to the Goldilocks problem of programming languages.

Observer the simple TypeScript function that checks if all letters in a string are unique:
```typescript
const isUnique1 = (str:string) : boolean => {
    let contains:Map<string, boolean> = new Map();

    for (let i=0; i < str.length; i++) {
        if (contains.get(str[i])) {
            return false;
        } else {
            contains.set(str[i], true);
        }
    }

    return true;
}

console.log(isUnique1('abcde'));  // prints true
console.log(isUnique1('abcdea')); // prints false
```

This code may strike an unattentive reader as C/C++ due to the myriad of types but the multiple object-oriented methods invoke a Pythonic feel. Combined, TypeScript truly felt like an almost perfect blend between C/C++ and Python through such similar conventions being present among each language. TypeScript was not too rigid nor was it too loose. TypeScript felt **just right**.