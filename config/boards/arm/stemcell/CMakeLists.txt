# SPDX-License-Identifier: Apache-2.0
# Copyright (c) 2021 Mega Mind

set_property(GLOBAL APPEND PROPERTY extra_post_build_commands
  COMMAND ${PYTHON_EXECUTABLE} ${ZEPHYR_BASE}/../tools/uf2/utils/uf2conv.py
  -c
  -b 0x08010000
  -f 0x57755a57
  -o ${PROJECT_BINARY_DIR}/${CONFIG_KERNEL_BIN_NAME}.uf2
  ${PROJECT_BINARY_DIR}/${CONFIG_KERNEL_BIN_NAME}.bin
)
