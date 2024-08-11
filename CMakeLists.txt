idf_component_register(REQUIRES esp_netif asio esp_timer)
if(CONFIG_LINK_TASK_AFFINITY_NO_AFFINITY)
  set(LINK_ESP_TASK_CORE_ID tskNO_AFFINITY)
elseif(CONFIG_LINK_TASK_AFFINITY_CPU0)
  set(LINK_ESP_TASK_CORE_ID 0)
elseif(CONFIG_LINK_TASK_AFFINITY_CPU1)  
  set(LINK_ESP_TASK_CORE_ID 1)
endif()

target_compile_definitions(${COMPONENT_LIB} INTERFACE LINK_ESP_TASK_CORE_ID=${LINK_ESP_TASK_CORE_ID})

include(link/AbletonLinkConfig.cmake)
target_link_libraries(${COMPONENT_TARGET} INTERFACE Ableton::Link)
