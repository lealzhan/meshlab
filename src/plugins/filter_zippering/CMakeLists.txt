include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  )

QT5_WRAP_CPP(moc_files filter_zippering.h)

set(filter_zippering_SRCS
  filter_zippering.cpp
  ${moc_files}
  )

add_library(filter_zippering SHARED ${filter_zippering_SRCS})
target_link_libraries(filter_zippering ${QT_LIBRARIES} ${OPENGL_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
install(TARGETS filter_zippering
  RUNTIME DESTINATION ${BIN_DIR}
  LIBRARY DESTINATION ${LIB_DIR}
  ARCHIVE DESTINATION ${LIB_DIR})

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
