configure_file(${CMAKE_CURRENT_SOURCE_DIR}/GMXRC.cmakein      ${CMAKE_CURRENT_BINARY_DIR}/GMXRC @ONLY)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/GMXRC.bash.cmakein ${CMAKE_CURRENT_BINARY_DIR}/GMXRC.bash @ONLY)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/GMXRC.csh.cmakein  ${CMAKE_CURRENT_BINARY_DIR}/GMXRC.csh @ONLY)
configure_file(${CMAKE_CURRENT_SOURCE_DIR}/GMXRC.zsh.cmakein  ${CMAKE_CURRENT_BINARY_DIR}/GMXRC.zsh @ONLY)

install(PROGRAMS ${CMAKE_CURRENT_BINARY_DIR}/GMXRC      DESTINATION ${BIN_INSTALL_DIR} COMPONENT runtime)
install(PROGRAMS ${CMAKE_CURRENT_BINARY_DIR}/GMXRC.bash DESTINATION ${BIN_INSTALL_DIR} COMPONENT runtime)
install(PROGRAMS ${CMAKE_CURRENT_BINARY_DIR}/GMXRC.zsh  DESTINATION ${BIN_INSTALL_DIR} COMPONENT runtime)
install(PROGRAMS ${CMAKE_CURRENT_BINARY_DIR}/GMXRC.csh  DESTINATION ${BIN_INSTALL_DIR} COMPONENT runtime)

file(GLOB EXTRA_SCRIPTS completion.*)
install(FILES ${EXTRA_SCRIPTS} DESTINATION ${BIN_INSTALL_DIR} COMPONENT runtime)

install(PROGRAMS ${CMAKE_CURRENT_SOURCE_DIR}/demux.pl      DESTINATION ${BIN_INSTALL_DIR} COMPONENT runtime)
install(PROGRAMS ${CMAKE_CURRENT_SOURCE_DIR}/xplor2gmx.pl  DESTINATION ${BIN_INSTALL_DIR} COMPONENT runtime)

