set(AM263X_SOURCE_DIR ${ZEPHYR_HAL_TI_MODULE_DIR}/am263x/source)
set(AM263X_SOURCE_KERNELS_DIR ${AM263X_SOURCE_DIR}/kernel)

if(CONFIG_SOC_SERIES_AM263X)
  zephyr_library()

  zephyr_include_directories(
    ${AM263X_SOURCE_DIR}
    ${AM263X_SOURCE_DIR}/drivers
  )

  zephyr_compile_definitions(
    SOC_AM263X
    DebugP_ASSERT_ENABLED=0
    DebugP_LOG_ENABLED=0
  )

  zephyr_library_sources(
    ${AM263X_SOURCE_DIR}/drivers/edma/v0/edma.c
    )

endif() # CONFIG_SOC_SERIES_AM263X
