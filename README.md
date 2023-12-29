# ![Logo](chrome/app/theme/chromium/product_logo_64.png) Chromium

> Chromium is an open-source browser project that aims to build a safer, faster,
and more stable way for all users to experience the web.
(Source: [chromium.org](https://www.chromium.org))

Here you can find some of my related work. Feel free to use it.

# Removing extra includes
## Trivial cases
I use the following tool: https://source.chromium.org/chromium/chromium/src/+/HEAD:tools/clang/scripts/analyze_includes.py  
Google data: https://commondatastorage.googleapis.com/chromium-browser-clang/include-analysis.html  
Each of the following branches (plus main) contains its own up-to-date data in **.eii/** directory.
### Active
* Removing extra <map> include in base/supports_user_data.h: [branch](https://github.com/efficiencyisimportant/chromium/tree/remove_map_include_in_base_supports_user_data.h)  
  Basically it has nearly zero impact: total build size 372,212,777,233 bytes -> 372,212,712,598 bytes, "Per-File Analysis" table is pretty the same.  
  Just to get things in order.
* Remove extra includes of base/supports_user_data.h: [branch](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_includes_base_supports_user_data.h)  
  Total build size: 372,212,777,233 bytes -> 372,122,223,975 bytes (-0.02%)  
  Probably that's all trivial changes we can make to base/supports_user_data.h
* Remove an extra include of partition_alloc/partition_alloc.h: [branch](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_partition_alloc.h_include)  
  Insignificant impact on total build size: 372,212,777,233 bytes -> 372,198,958,977 bytes (-0.004%). But meaningful impact for the top 1000 in sum both for "Per-File Analysis" and for "Per-Edge Analysis" (0.5% and 1.3% respectively).
* Remove storage_partition extra includes from render_frame_host_impl.h: [branch](https://github.com/efficiencyisimportant/chromium/tree/remove_storage_partition_extra_includes_in_render_frame_host_impl.h)  
  Total build size: 372,212,777,233 bytes -> 371,114,071,734 bytes (-0.3%).  
  render_frame_host_impl.h moved from 20th place to 53rd.

