# Opinionated File Structure For React Apps

<br/><br/>

## Two Things You Ought To Know First

**1. Opinionated -** Since there is no "right" file structure, there is always going to be debates what file structure works best. That said, if you're looking for an opinionated guide to React conventions, and application structure, step right in. This style guide presents preferred conventions and, as importantly, explains why. For that reason the goal of this guide is to eliminate any potential debates when it comes to file structures. Remember there is no magic bullet for this or a general recipe which fits for all projects.

**2. Focus -** This guide does not focus on file structure of React component libraries, although most of the practices mentioned here are applicable. Instead, it focuses on API-facing medium to large CRUD (Create, Read, Update, Delete) React apps that deal with data fetching, authentication, client and server states, etc.
The goal of this article is to help developers by proposing a scalable and maintainable structure.

<br/><br/>

# Motivation
Knowing what exact file structure and naming convention to adopt right out the the gate can save you and your team a lot of time and effort. Not knowing this could have you wade through many different refactors until you get to the structure that feels right for you and your team.

What I mean by "feels right" is that there is no right file structure. Every team and every project is in a certain way different. That means that each team should pick a file structure that works for them.
[React official docs](https://reactjs.org/docs/faq-structure.html) tells you not to think about file structure too much and to figure it out as the app grows. In my experience, unfortunately this approach did not work out well and for that reason I'd like to share the knowledge I gained during this time. 

<br/><br/>

# The Problem

**1. File structure -** you want to know what your file structure will look like right out the gate. You want a time-proof file structure that will scale well without having to refactor eventually as the app grows. You googled it up and read dozens of articles. You found most of them vague without explaining too much if at all, what the exact benefits each file structure has and what are the trade-offs if any.

**2. Refactors due to app growth -** you want to avoid any potential refactors due to application growth over time. More often than not, API-facing React apps are heavily form oriented. Such apps can grow very fast and very wide. Not thinking too much about file structure from the get-go can lead to refactors
even before you know it due to fast growing nature of these types of apps.

**3. Naming -** you want to know what naming conventions files and folders will have from day one. At the start, names can be very generic without any repercussions however as the app grows, sometimes names have to be more specific with more context included in the names per sei. In order to avoid having to rename, it's a good idea to adopt a convention that will still have legs even two years from the bootstrapping.

<br/><br/>

# This Solution

This solution follows:
1. Folders-by-feature
2. LIFT principle
3. Accent on collocation

<br/><br/>

## Folders by feature

Every file regardless of type and use intent should always be collocated with other relevant files that compose a certain feature. 
The one and only reason a file should not be collocated is in case the file is shared across multiple features, therefore isn't tailored towards any specific feature.

Essentially a file belongs either to "Features" folder or "Shared".

Why? A developer can locate the code and identify what each file represents at a glance.

Why? The LIFT guidelines are all covered.

Why? Helps reduce the application from becoming cluttered through organizing the content and keeping them aligned with the LIFT guidelines.

Why? When there are a lot of files per feature, for example 10+, locating them is easier with a consistent folder-by-feature structure.

<br/><br/>

## LIFT Principle

Lift stands for:

### L: Locate. Make locating files quick and intuitive.

Consider creating a folder for a component when it has multiple accompanying files (types, interfaces, tests, validations, mocks, utilities etc).

Why? To work efficiently you must be able to find files quickly, especially when you do not know (or do not remember) the file names. Keeping related files near each other in an intuitive location saves time. A descriptive folder structure makes a world of difference to you and the people who come after you

Why? Helps keep the application structure small and easy to maintain in the early stages, while being easy to evolve as the application grows.

Why? Container components often have many companion files and can clutter a folder quickly.

### I: Identify. Name the file such that you instantly know what it contains and represents

Spend less time hunting and pecking for code, and become more efficient. Longer file names are far better than short-but-obscure abbreviated names.

Naming conventions are hugely important to maintainability and readability. This guide recommends naming conventions for the file name and the type name.

### F: Flat. Keep a flat folder structure as long as possible.

Consider creating sub-folders when a folder reaches nine or more files.

Psychologists believe that humans start to struggle when the number of adjacent interesting things exceeds nine. So when a folder has nine or more files, it may be time to create subfolders. (I don't know if this is true about humans but a number has to be picked so might as well be nine)

Use dots to separate the descriptive name from the type.

Use consistent type names for all components following a pattern that describes the component's feature then its type. A recommended pattern is `Update.type.ts`

Use consistent names for all assets named after what they represent.

Use upper camel case for file names.

Use conventional type suffix names including `.type`, `.test`, `.validation`, `.utility` etc. Invent additional type names if you must but take care not to create too many.

Why? Names of folders and files should clearly convey their intent.

Why? Type names provide a consistent way to quickly identify what is in the file.

Why? Type names make it easy to find a specific file type using an editor or IDE's fuzzy search techniques.

Why? Unabbreviated type names such as `.test` are descriptive and unambiguous.

Why? Type names provide pattern matching for any automated tasks.

Why? Consistent conventions make it easy to quickly identify and reference assets of different types.

### T: T-DRY (Try to be DRY)

Do be DRY (Don't Repeat Yourself).

Avoid being so DRY that you sacrifice readability.

Why? Being DRY is important, but not crucial if it sacrifices the other elements of LIFT. That's why it's called T-DRY

<br/><br/>

# Example


```
src
    Shared
        Components
            Form
                TextField.tsx
                TextField.test.tsx
                SelectMenu.tsx
                SelectMenu.test.tsx
                Checkbox.tsx
                Checkbox.test.tsx
                FormTitle.tsx  
            Layout
                ListLayout.tsx
                ListLayoutBar.tsx
                CreateLayout.tsx
                Navigation.tsx
                NavigationLinkButton.tsx
                NavigationList.tsx
                NavigationLogoutButton.tsx
        Contexts
            GlobalStateProvider.tsx
            AuthenticationProvider.tsx
        Hooks
            useSomething.ts
            useFetch.ts
        Types
            ReusableItem.type.ts
        Utilities
            Assertions.utility.ts
            Getters.utility.ts
    Features
        FeatureTwo
            Create
                Create.container.tsx
                Create.container.test.tsx
                Create.types.ts
                Create.validations.ts
                Create.fields.tsx
                Create.utilities.ts
            List
                List.container.tsx
                List.container.test.tsx
                List.types.ts
            Update
                Update.container.tsx
                Update.container.test.tsx
                Update.types.ts
                Update.validations.ts
                Update.fields.tsx
                Update.utilities.ts
            Shared
                Shared.types.ts
                Shared.validations.tsx
                Address.fields.tsx
                Bank.fields.tsx
                Shared.utilities.ts
            FeatureTwo.routes.tsx
```
