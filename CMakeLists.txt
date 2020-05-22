idf_component_register(INCLUDE_DIRS "link/include"
                       REQUIRES asio)

if(NOT DEFINED LINK_ESP_TASK_CORE_ID)
  set(LINK_ESP_TASK_CORE_ID tskNO_AFFINITY)
endif()
target_compile_definitions(${COMPONENT_LIB} PRIVATE LINK_ESP_TASK_CORE_ID=${LINK_ESP_TASK_CORE_ID})
