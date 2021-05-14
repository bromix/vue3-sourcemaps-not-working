# vue3-sourcemaps-not-working
Example project to compare SourceMaps between Vue2 and Vue3. Both projects are identical in structure and functionality. One project uses Vue v2.X (vue2app) and the other uses Vue v3.X (vue3app).

## The problem
Breakpoints set in the Vue v2.x project work properly thanks to source maps and allow direct debugging in the code.

An identical project with Vue v3.x can be started but not debugged using breakpoints. The source maps behave differently compared to those created with Vue v2.x.

In direct comparison the source maps are also created differently. The problem occurs only with Vue files. These are divided into several source maps. A typescript file, which was also imported in a Vue file, can be debugged without problems (breakpoints work).

## Breakpoint/debugger
### Vue v3
If we now use a simple "debugger" statement (breakpoint is not triggered) we can see that the source files is wrong. We are not in the original Vue file, but in a detached version of it.
![image](https://user-images.githubusercontent.com/4136891/118274513-8356e880-b4c5-11eb-91cd-dcdd000fea2c.png)


### Vue v2
In direct comparison the project in Vue v2, we stop at the right position in the Vue file.
![image](https://user-images.githubusercontent.com/4136891/118275023-2a3b8480-b4c6-11eb-8af2-25c375646a82.png)

## Source-Maps
### Vue v3
The source maps with Vue v3 are different and do not reflect the same structure as in Vue v2. The mapping does not match.
![image](https://user-images.githubusercontent.com/4136891/118275895-4d1a6880-b4c7-11eb-9d39-bdd3942bd455.png)

### Vue v2
App.vue, which has the same name as the original Vue file, contains the script section. We will see the same in Home.vue, which is also just the script section from the original Vue file.
![image](https://user-images.githubusercontent.com/4136891/118275284-87cfd100-b4c6-11eb-865d-fac528f71186.png)
