My personal [dwm](https://dwm.suckless.org/) setup with [dwm-flexipatch](https://github.com/bakkeby/dwm-flexipatch)
<br>


This dwm 6.4 (e81f17d, 2023-04-09) side project has a different take on dwm patching. It uses preprocessor directives to decide whether or not to include a patch during build time. Essentially this means that this build, for better or worse, contains both the patched _and_ the original code. The aim being that you can select which patches to include and the build will contain that code and nothing more. Due to the complexity of some of the patches dwm-flexipatch has diverged from mainstream dwm by making some core patches non-optional for maintenance reasons. For the classic dwm-flexipatch build refer to branch [dwm-flexipatch-1.0](https://github.com/bakkeby/dwm-flexipatch/tree/dwm-flexipatch-1.0).

For example to include the `alpha` patch then you would only need to flip this setting from 0 to 1 in [patches.h](https://github.com/bakkeby/dwm-flexipatch/blob/master/patches.def.h):
```c
#define BAR_ALPHA_PATCH 1
```

So if you have ever been curious about trying out dwm, but have been discouraged by manual patching, then this may be a good starting point to see what a "fully fledged" dwm can look like. Want to try out the `pertag` patch? Just flip a config and recompile. Once you have found out what works for you and what doesn't then you should be in a better position to choose patches should you want to start patching from scratch.

Alternatively if you have found the patches you want, but don't want the rest of the flexipatch entanglement on your plate then you may want to have a look at [flexipatch-finalizer](https://github.com/bakkeby/flexipatch-finalizer); a custom pre-processor tool that removes all the unused flexipatch code leaving you with a build that contains the patches you selected.

Refer to [https://dwm.suckless.org/](https://dwm.suckless.org/) for details on the dwm window manager, how to install it and how it works.

If you are experiencing issues then you may want to check out the [Known Issues](https://github.com/bakkeby/dwm-flexipatch/discussions/categories/known-issues) discussion category.

Browsing patches? There is a [map of patches](https://coggle.it/diagram/X9IiSSM6PTWOM9Wz) diagram which tries to organise patches into categories.
