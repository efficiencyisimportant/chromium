# ![Logo](chrome/app/theme/chromium/product_logo_64.png) Chromium

> Chromium is an open-source browser project that aims to build a safer, faster,
and more stable way for all users to experience the web.
(Source: [chromium.org](https://www.chromium.org))

Here you can find some of my related work. Feel free to use it.

# Removing extra includes
## Trivial cases
The following tool was used: https://source.chromium.org/chromium/chromium/src/+/HEAD:tools/clang/scripts/analyze_includes.py  
Google data: https://commondatastorage.googleapis.com/chromium-browser-clang/include-analysis.html  
Each of the following branches (plus main) contains its own up-to-date data in **.eii/** directory.
| Branch | Total build size (GB / profit %) | Per-File, sum(Added Size) of top1000 (GB / profit %) | Per-Edge, sum(Added Size) of top1000 (GB / profit %) | Notes | Upstream |
|--------|----------------------------------|------------------------------------------------------|------------------------------------------------------|-------|----------|
| [main](https://github.com/efficiencyisimportant/chromium/tree/main) | 372.213 / 0.00 | 607.882 / 0.00 | 247.41 / 0.00 | Base | --- | 
| [remove_extra_style_sheet_contents.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_style_sheet_contents.h_include) | 368.87 / 0.90 | 590.725 / 2.82 | 234.565 / 5.19 |  |  |
| [remove_extra_inspector_audits_issue.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_inspector_audits_issue.h_include) | 369.97 / 0.60 | 601.39 / 1.07 | 241.745 / 2.29 |  |  |
| [remove_extra_chrome_track_event.pbzero.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_chrome_track_event.pbzero.h_include) | 370.945 / 0.34 | 604.527 / 0.55 | 245.478 / 0.78 |  |  |
| [remove_storage_partition_extra_includes_in_render_frame_host_impl.h](https://github.com/efficiencyisimportant/chromium/tree/remove_storage_partition_extra_includes_in_render_frame_host_impl.h) | 371.114 / 0.30 | 603.07 / 0.79 | 244.241 / 1.28 | render_frame_host_impl.h moved from 20th place to 53rd |  |
| [remove_extra_url_loader_network_service_observer.mojom.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_url_loader_network_service_observer.mojom.h_include) | 371.416 / 0.21 | 602.886 / 0.82 | 242.998 / 1.78 |  |  |
| [remove_extra_chrome_track_event.pbzero.h_include3](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_chrome_track_event.pbzero.h_include3) | 371.889 / 0.09 | 607.596 / 0.05 | 247.544 / -0.05 |  |  |
| [remove_extra_root_store.pb.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_root_store.pb.h_include) | 371.928 / 0.08 | 605.802 / 0.34 | 245.722 / 0.68 |  |  |
| [remove_extra_includes_in_css_value_id_mappings_generated.h](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_includes_in_css_value_id_mappings_generated.h) | 371.903 / 0.08 | 606.185 / 0.28 | 245.921 / 0.60 |  |  |
| [remove_extra_includes_in_cookie_manager.mojom](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_includes_in_cookie_manager.mojom) | 371.927 / 0.08 | 607.264 / 0.10 | 247.12 / 0.12 |  |  |
| [remove_extra_http_response_headers.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_http_response_headers.h_include) | 371.922 / 0.08 | 606.768 / 0.18 | 246.649 / 0.31 |  |  |
| [remove_extra_chrome_track_event.pbzero.h_include2](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_chrome_track_event.pbzero.h_include2) | 371.966 / 0.07 | 607.569 / 0.05 | 247.347 / 0.03 |  |  |
| [remove_extra_to_v8_for_core.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_to_v8_for_core.h_include) | 371.972 / 0.06 | 606.904 / 0.16 | 246.864 / 0.22 |  |  |
| [remove_extra_shared_url_loader_factory.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_shared_url_loader_factory.h_include) | 371.987 / 0.06 | 606.785 / 0.18 | 246.462 / 0.38 |  |  |
| [remove_extra_render_widget_host_impl.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_render_widget_host_impl.h_include) | 372.029 / 0.05 | 607.704 / 0.03 | 247.384 / 0.01 |  |  |
| [remove_extra_remote_media_stream_track_adapter.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_remote_media_stream_track_adapter.h_include) | 372.045 / 0.05 | 607.256 / 0.10 | 246.815 / 0.24 |  |  |
| [remove_extra_proxy_resolver.mojom_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_proxy_resolver.mojom_include) | 372.021 / 0.05 | 607.668 / 0.04 | 247.282 / 0.05 |  |  |
| [remove_extra_property_set_css_style_declaration.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_property_set_css_style_declaration.h_include) | 372.041 / 0.05 | 607.067 / 0.13 | 246.692 / 0.29 |  |  |
| [remove_extra_core_page_page.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_core_page_page.h_include) | 372.033 / 0.05 | 607.393 / 0.08 | 247.139 / 0.11 |  |  |
| [remove_extra_url_formatter.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_url_formatter.h_include) | 372.067 / 0.04 | 607.305 / 0.09 | 247.077 / 0.13 |  |  |
| [remove_extra_skia_paint_image_generator.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_skia_paint_image_generator.h_include) | 372.073 / 0.04 | 607.767 / 0.02 | 246.986 / 0.17 |  |  |
| [remove_extra_service_worker_keepalive.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_service_worker_keepalive.h_include) | 372.074 / 0.04 | 607.246 / 0.10 | 246.894 / 0.21 |  |  |
| [remove_extra_sequenced_task_runner.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_sequenced_task_runner.h_include) | 372.074 / 0.04 | 607.859 / 0.00 | 247.097 / 0.13 |  |  |
| [remove_extra_permissions_policy.mojom.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_permissions_policy.mojom.h_include) | 372.08 / 0.04 | 607.566 / 0.05 | 247.165 / 0.10 |  |  |
| [remove_extra_labels_node_list.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_labels_node_list.h_include) | 372.067 / 0.04 | 608.475 / -0.10 | 247.852 / -0.18 |  |  |
| [remove_extra_frame.mojom-shared.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_frame.mojom-shared.h_include) | 372.056 / 0.04 | 607.464 / 0.07 | 247.126 / 0.11 |  |  |
| [remove_extra_delay_policy.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_delay_policy.h_include) | 372.059 / 0.04 | 607.453 / 0.07 | 247.056 / 0.14 |  |  |
| [remove_extra_browser_context.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_browser_context.h_include) | 372.073 / 0.04 | 607.234 / 0.11 | 246.884 / 0.21 |  |  |
| [remove_extra_autocomplete_scoring_model_service.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_autocomplete_scoring_model_service.h_include) | 372.058 / 0.04 | 607.613 / 0.04 | 247.256 / 0.06 |  |  |
| [remove_extra_web_app_command_scheduler.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_web_app_command_scheduler.h_include) | 372.111 / 0.03 | 607.481 / 0.07 | 247.227 / 0.07 |  |  |
| [remove_extra_vr_service.mojom-blink.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_vr_service.mojom-blink.h_include) | 372.106 / 0.03 | 607.723 / 0.03 | 247.443 / -0.01 |  |  |
| [remove_extra_segmentation_platform_result.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_segmentation_platform_result.h_include) | 372.101 / 0.03 | 607.721 / 0.03 | 247.298 / 0.05 |  |  |
| [remove_extra_render_process_host.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_render_process_host.h_include) | 372.091 / 0.03 | 607.632 / 0.04 | 247.312 / 0.04 |  |  |
| [remove_extra_permissions_policy.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_permissions_policy.h_include) | 372.092 / 0.03 | 607.663 / 0.04 | 247.482 / -0.03 |  |  |
| [remove_extra_paint_timing_detector.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_paint_timing_detector.h_include) | 372.118 / 0.03 | 607.732 / 0.02 | 247.247 / 0.07 |  |  |
| [remove_extra_layout_box_model_object.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_layout_box_model_object.h_include) | 372.117 / 0.03 | 607.71 / 0.03 | 247.236 / 0.07 |  |  |
| [remove_extra_frame_load_request.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_frame_load_request.h_include) | 372.091 / 0.03 | 608.048 / -0.03 | 247.507 / -0.04 |  |  |
| [remove_extra_connectors_manager.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_connectors_manager.h_include) | 372.114 / 0.03 | 607.677 / 0.03 | 247.301 / 0.04 |  |  |
| [remove_extra_browser_accessibility_manager.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_browser_accessibility_manager.h_include) | 372.087 / 0.03 | 607.713 / 0.03 | 247.339 / 0.03 |  |  |
| [remove_extra_web_contents.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_web_contents.h_include) | 372.128 / 0.02 | 607.873 / 0.00 | 247.563 / -0.06 |  |  |
| [remove_extra_surface_layer.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_surface_layer.h_include) | 372.133 / 0.02 | 607.759 / 0.02 | 247.374 / 0.01 |  |  |
| [remove_extra_storage_partition_impl.h_include_in_render_process_host_impl.h](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_storage_partition_impl.h_include_in_render_process_host_impl.h) | 372.125 / 0.02 | 607.628 / 0.04 | 247.324 / 0.03 |  |  |
| [remove_extra_shared_url_loader_factory.h_include_2](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_shared_url_loader_factory.h_include_2) | 372.127 / 0.02 | 607.775 / 0.02 | 247.19 / 0.09 |  |  |
| [remove_extra_includes_base_supports_user_data.h](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_includes_base_supports_user_data.h) | 372.122 / 0.02 | 607.579 / 0.05 | 247.201 / 0.08 | Probably that's all trivial changes we can make to base/supports_user_data.h |  |
| [remove_map_include_in_base_supports_user_data.h](https://github.com/efficiencyisimportant/chromium/tree/remove_map_include_in_base_supports_user_data.h) | 372.213 / 0.00 | 607.896 / -0.00 | 247.425 / -0.01 | Just to get things in order |  |
| [remove_extra_partition_alloc.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_partition_alloc.h_include) | 372.199 / 0.00 | 604.753 / 0.51 | 244.187 / 1.30 | Cool impact for the top1000 files and edges |  |
| [remove_extra_css_style_sheet.h_include](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_css_style_sheet.h_include) | 372.213 / 0.00 | 610.752 / -0.47 | 250.348 / -1.19 |  |  |
| [remove_extra_chrome_track_event.pbzero.h_include4](https://github.com/efficiencyisimportant/chromium/tree/remove_extra_chrome_track_event.pbzero.h_include4) | 372.208 / 0.00 | 608.258 / -0.06 | 247.849 / -0.18 |  |  |
