include(ECMMarkAsTest)

find_package(Qt${QT_MAJOR_VERSION}Test CONFIG REQUIRED)

########### next target ###############

add_executable(testlunar testlunar.cpp testlunar.h)
add_test(NAME testlunar COMMAND testlunar)
ecm_mark_as_test(testlunar)
target_link_libraries(testlunar KF5Holidays Qt${QT_MAJOR_VERSION}::Test)

########### next target ###############

add_executable(testseasons testseasons.cpp testseasons.h)
add_test(NAME testseasons COMMAND testseasons)
ecm_mark_as_test(testseasons)
target_link_libraries(testseasons KF5Holidays Qt${QT_MAJOR_VERSION}::Test)

########### next target ###############

add_executable(testsunriseset testsunriseset.cpp testsunriseset.h)
add_test(NAME testsunriseset COMMAND testsunriseset)
ecm_mark_as_test(testsunriseset)
target_link_libraries(testsunriseset KF5Holidays Qt${QT_MAJOR_VERSION}::Test)

########### next target ###############

add_executable(testzodiac testzodiac.cpp)
add_test(NAME testzodiac COMMAND testzodiac)
ecm_mark_as_test(testzodiac)
target_link_libraries(testzodiac KF5Holidays Qt${QT_MAJOR_VERSION}::Test)

########### next target ###############

add_executable(testholidayregion testholidayregion.cpp testholidayregion.h)
add_test(NAME testholidayregion COMMAND testholidayregion)
set_target_properties(testholidayregion PROPERTIES COMPILE_FLAGS -DKDESRCDIR="\\"${CMAKE_CURRENT_SOURCE_DIR}/\\"")

# if(NOT EXCLUDE_DEPRECATED_BEFORE_AND_AT STREQUAL "CURRENT" AND
#    EXCLUDE_DEPRECATED_BEFORE_AND_AT VERSION_LESS 5.93.0)
#    add_test(NAME testholidayregion COMMAND testholidayregion)
#    set_target_properties(testholidayregion PROPERTIES COMPILE_FLAGS -DKDESRCDIR="\\"${CMAKE_CURRENT_SOURCE_DIR}/\\"")   
# endif()

ecm_mark_as_test(testholidayregion)
target_link_libraries(testholidayregion KF5Holidays Qt${QT_MAJOR_VERSION}::Test)
