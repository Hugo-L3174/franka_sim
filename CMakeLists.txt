cmake_minimum_required(VERSION 3.1)

project(mc_panda_mujoco VERSION 1.0.0)

find_package(mc_mujoco REQUIRED)
find_package(mc_panda REQUIRED)

set(SHARE_DESTINATION "${CMAKE_INSTALL_PREFIX}/share/mc_panda/mujoco/")

install(DIRECTORY assets DESTINATION "${SHARE_DESTINATION}")
install(DIRECTORY meshes DESTINATION "${SHARE_DESTINATION}")
install(FILES franka_panda.xml DESTINATION "${SHARE_DESTINATION}" RENAME panda_hand.xml)

configure_file(mc_mujoco/panda_hand.in.yaml "${CMAKE_CURRENT_BINARY_DIR}/panda_hand.yaml")
install(FILES "${CMAKE_CURRENT_BINARY_DIR}/panda_hand.yaml" DESTINATION "${MC_MUJOCO_SHARE_DESTINATION}")
