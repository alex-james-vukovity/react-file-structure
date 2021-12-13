# Opinionated File Structure For React Apps

<br/><br/>

## Two Things You Ought To Know First

**1. Opinionated -** Since there is no "right" file structure, there is always going to be debates what file structure works best. That said, if you're ooking for an opinionated guide to React conventions, and application structure, step right in. This style guide presents preferred conventions and, as importantly, explains why. For that reason the goal of this guide is to eliminate any potential debates when it comes to file structures. Remember there is no magic bullet for this or a general recipe which fits for all projects.

**2. Focus -** This guide does not focus on file structure of React component libraries, although most of the practices mentioned here are applicable. Instead, it focuses on API-facing medium to large CRUD (Create, Read, Update, Delete) React apps that deal with data fetching, authentication, client and server states, etc.
The goal of this article is to help developers by proposing a scalable and maintainable structure.

<br/><br/>

# Motivation
Knowing what exact file structure and naming convention to adopt right out the the gate can save you and your team a lot of time and effort. Not knowing this could have you wade through many different refactors until you get to the structure that feels right for you and your team.

What I mean by "feels right" is that there is no right file strucutre. Every team and every project is in a certain way different. That means that each team should pick a file structure that works for them.
[React official docs](https://reactjs.org/docs/faq-structure.html) tells you not to think about file structure too much and to figure it out as the app grows. In my experience, unfortunately this approach did not work out well and for that reason I'd like to share the knowledge I gained during this time. 

<br/><br/>

# The Problem

**1. File structure -** you want to know what your file structure will look like right out the gate. You want a time-proof file structure that will scale well without having to refactor eventually as the app grows. You googled it up and read dozens of articles. You found most of them vague without explaining too much if at all, what the exact benefits each file structure has and what are the trade-offs if any.

**2. Refactors due to app growth -** you want to avoid any potential refactors due to application growth over time. More often than not, API-facing React apps are heavily form oriented. Such apps can grow very fast and very wide. Not thinking too much about file structure from the get-go can lead to refactors
even before you know it due to fast growing nature of these type of apps.

**3. Naming -** you want to know what naming convetions files and folders will have from day one. At the start, names can be very generic without any repercussions however as the app grows, sometimes names have to be more specific with more context included in the names per sei. In order to avoid having to rename, it's a good idea to adopt a convetion that will still have legs even two years from the bootstrapping.

<br/><br/>

# This Solution

<br/><br/>

This solution follows:
1. Folders-by-feature
2. LIFT principle
3. Heavy collocation

## Folders by feature

Every file regardless of type and use intent should always be collocated with other relevant files that comprise the a certain feature. 
The one and only reason a file should not be collocated is in case the file is shared across multiple features, therefore isn't tailered towards any specific feature.

Esssentialy a file belongs either to "Features" folder or "Shared".

Why? A developer can locate the code and identify what each file represents at a glance.

Why? The LIFT guidelines are all covered.

Why? Helps reduce the application from becoming cluttered through organizing the content and keeping them aligned with the LIFT guidelines.

Why? When there are a lot of files, for example 10+, locating them is easier with a consistent folder structure and more difficult in a flat structure.

## LIFT Principle

Lift stands for:

### L: Locate. 

Make locating files quick and intutive. Consider creating a folder for a component when it has multiple accompanying files (interface, test, validation, mock, utilities etc).

Why? To work efficiently you must be able to find files quickly, especially when you do not know (or do not remember) the file names. Keeping related files near each other in an intuitive location saves time. A descriptive folder structure makes a world of difference to you and the people who come after you

Why? Helps keep the application structure small and easy to maintain in the early stages, while being easy to evolve as the application grows.

Why? Contianer components often have many companion files and can clutter a folder quickly.

### I: Identify. Name the file such that you instantly know what it contains and represents

Spend less time hunting and pecking for code, and become more efficient. Longer file names are far better than short-but-obscure abbreviated names.

Naming conventions are hugely important to maintainability and readability. This guide recommends naming conventions for the file name and the symbol name.

### F: Flat. Keep a flat folder structure as long as possible.

Consider creating sub-folders when a folder reaches nine or more files.

Psychologists believe that humans start to struggle when the number of adjacent interesting things exceeds nine. So when a folder has nine or more files, it may be time to create subfolders. (I don't know if this is true btw about humans but a number has to be picked so might as well be nine)

Use dots to separate the descriptive name from the type.

Use consistent type names for all components following a pattern that describes the component's feature then its type. A recommended pattern is FeatureOne.type.ts.

Use consistent names for all assets named after what they represent.

Use upper camel case for file names.

Use conventional type suffix names including .interface, .component, .mock, .test, .module, .validation, .utility. Invent additional type names if you must but take care not to create too many.

Why: Names of folders and files should clearly convey their intent.

Why? Type names provide a consistent way to quickly identify what is in the file.

Why? Type names make it easy to find a specific file type using an editor or IDE's fuzzy search techniques.

Why? Unabbreviated type names such as .interface are descriptive and unambiguous.

Why? Type names provide pattern matching for any automated tasks.

Why? Consistent conventions make it easy to quickly identify and reference assets of different types.

Naming utility function

#### A/HC/LC Pattern

There is a useful pattern to follow when naming functions:

```
prefix? + action (A) + high context (HC) + low context? (LC)
```

Take a look at how this pattern may be applied in the table below.

| Name                   | Prefix   | Action (A) | High context (HC) | Low context (LC) |
| ---------------------- | -------- | ---------- | ----------------- | ---------------- |
| `getUser`              |          | `get`      | `User`            |                  |
| `getUserMessages`      |          | `get`      | `User`            | `Messages`       |
| `handleClickOutside`   |          | `handle`   | `Click`           | `Outside`        |
| `shouldDisplayMessage` | `should` | `Display`  | `Message`         |                  |

Action: get | set | reset | fetch | handle | compose | remove | delete

Prefix: is | should | has | min | max | prev | next

### T: T-DRY (Try to be DRY)

Do be DRY (Don't Repeat Yourself).

Avoid being so DRY that you sacrifice readability.

Why? Being DRY is important, but not crucial if it sacrifices the other elements of LIFT. That's why it's called T-DRY. For example, it's redundant to name a template hero-view.component.html because with the .html extension, it is obviously a view. But if something is not obvious or departs from a convention, then spell it out.

This means you should keep the structure as flat as possible, this makes possible to locate the files faster. But this is not a must rule, but a should.
Remember this aims to improve the development process. If something is not improving your team organization/productivity, etc., then don't use it, if it helps, use it.


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
                FormGrid.tsx
                FormGrid.Item.tsx
                FormGrid.Item.OneColumn.tsx
                FormGrid.Item.TwoColumns.tsx
                FormGrid.Item.ThreeColumns.tsx
            Layout
                ListLayout.tsx
                ListLayout.Bar.tsx
                CreateLayout.tsx
                CreateLayout.SubmitButton.tsx
                CreateLayout.ResetButton.tsx
                UpdateLayout.tsx
                UpdateLayout.CancelButton.tsx
                Navigation.tsx
                Navigation.LinkButton.tsx
                Navigation.List.tsx
                Navigation.LogoutButton.tsx
                ContentLoader.tsx
                Title.tsx
                SectionTitle.tsx
        Context
            GlobalState.tsx
            Authentication.tsx
        Hooks
            useSomething.ts
            useFetch.ts
        Interfaces
            UseParams.interface.ts
        Utilities
            JoinPaginationParams.utility.ts
    Features
        FeatureOne
            Create
                FeatureOne.Create.tsx
                FeatureOne.Create.test.tsx
                FeatureOne.Create.interface.ts
                FeatureOne.Create.validation.ts
                FeatureOne.Create.DedicatedFormPartial.fields.tsx
                FeatureOne.Create.mocks.ts
            List
                FeatureOne.List.tsx
                FeatureOne.List.test.tsx
                FeatureOne.List.interfaces.ts
                FeatureOne.List.mocks.ts
            Update
                FeatureOne.Update.tsx
                FeatureOne.Update.test.tsx
                FeatureOne.Update.interface.ts
                FeatureOne.Update.validation.ts
                FeatureOne.Update.DedicatedFormPartial.fields.tsx
                FeatureOne.Update.mocks.ts
            Shared
                FeatureOne.interface.ts
                FeatureOne.validation.tsx
                FeatureOne.SomeFormPartialOne.fields.tsx
                FeatureOne.SomeFormPartialTwo.fields.tsx
                FeatureOne.SomeFormPartialThree.fields.tsx
                FeatureOne.Assertions.utility.ts
            FeatureOne.Routes.tsx
```
