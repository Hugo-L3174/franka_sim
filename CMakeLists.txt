cmake_minimum_required(VERSION 3.10)

project(mc_panda_mujoco VERSION 1.0.0)

find_package(mc_mujoco REQUIRED)
find_package(mc_panda REQUIRED)

set(SHARE_DESTINATION "${CMAKE_INSTALL_PREFIX}/share/mc_panda/mujoco/")

install(DIRECTORY meshes DESTINATION "${SHARE_DESTINATION}")

install(FILES panda_default.xml DESTINATION "${SHARE_DESTINATION}")
install(FILES panda_foot.xml DESTINATION "${SHARE_DESTINATION}")
install(FILES panda_hand.xml DESTINATION "${SHARE_DESTINATION}")
install(FILES panda_helpup.xml DESTINATION "${SHARE_DESTINATION}")

configure_file(mc_mujoco/panda_hand.in.yaml "${CMAKE_CURRENT_BINARY_DIR}/panda_hand.yaml")
install(FILES "${CMAKE_CURRENT_BINARY_DIR}/panda_hand.yaml" DESTINATION "${MC_MUJOCO_SHARE_DESTINATION}")

configure_file(mc_mujoco/panda_default.in.yaml "${CMAKE_CURRENT_BINARY_DIR}/panda_default.yaml")
install(FILES "${CMAKE_CURRENT_BINARY_DIR}/panda_default.yaml" DESTINATION "${MC_MUJOCO_SHARE_DESTINATION}")

configure_file(mc_mujoco/panda_foot.in.yaml "${CMAKE_CURRENT_BINARY_DIR}/panda_foot.yaml")
install(FILES "${CMAKE_CURRENT_BINARY_DIR}/panda_foot.yaml" DESTINATION "${MC_MUJOCO_SHARE_DESTINATION}")

configure_file(mc_mujoco/panda_helpup.in.yaml "${CMAKE_CURRENT_BINARY_DIR}/panda_helpup.yaml")
install(FILES "${CMAKE_CURRENT_BINARY_DIR}/panda_helpup.yaml" DESTINATION "${MC_MUJOCO_SHARE_DESTINATION}")