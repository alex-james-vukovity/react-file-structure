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

This solution uses:
1. folders-by-feature-then-by-type 
2. adhering to LIFT 
3. heavy focus on collocation of relevant files


This means you should keep the structure as flat as possible, this makes possible to locate the files faster. But this is not a must rule, but a should one.
Remember this aims to improve the development process. If something is not improving your team organization/productivity, etc., then don't use it, if it helps, use it.

Let me talk about what each of these means.

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
                FeatureOne.GetSomething.utility.ts
            FeatureOne.Routes.tsx
```






