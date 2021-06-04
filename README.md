# Alternate Frontend for Udemy "NestJS Zero to Hero" by Ariel Weinberger

Check out [the course on Udemy](https://www.udemy.com/share/101ZIcAEUad1hTQH4F/), it's a very gently presented and enlightening intro to [NestJS](https://nestjs.com/).

Later on in the course Ariel provides a frontend, that isn't the subject of the course, but allows you to interact with the REST service, that is the main subject.

I found it required Python-2 to install 🐍 and 😱, and I also wanted to learn more about [NextJS](https://nextjs.org/) not because the name is so similar with NestJS, but because the people at Vercel seem to be incredibly smart. ([Case in point, SWR](https://swr.vercel.app/))

I tried to keep most of the code similar with Ariel's frontend, but this does have a few changes,
* the router is taken out of MobX and the NextJS router is used instead (it's a core part of their platform)
* the way the pages are set up is also different, also due to NextJS platform architecture
* I didn't really think RxJS was necessary in the create-task form, when a `useEffect` is all it seems to need
* Updated usage of MobX to avoid any warnings - coming from Redux that is a bit of a paradigm shift, and there are a lot of different version APIs to React/MobX.

One major downside, the component (that does `useRouter`) handles the 401 exception and reroutes to the login page. Ariel's solution is a lot better where the
`base-http-service` component handles that - no matter where it's called from. I think maybe routing is a higher level concern but this code just takes the
shortest path to making it work in that regard.

Also I'm terrible with Typescript and nearly gave up with trying to type things halfway through. 🤷‍♂️
