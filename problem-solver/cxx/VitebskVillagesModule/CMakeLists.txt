set(SOURCES
		"VitebskVillagesModule.cpp"
		"keynodes/keynodes.cpp"
		"agents/LargerVillageByPopulation.cpp"
		)

set(HEADERS
		"VitebskVillagesModule.hpp"
		"keynodes/keynodes.hpp"
		"agents/LargerVillageByPopulation.hpp"
		)

include_directories(
		${CMAKE_CURRENT_LIST_DIR}
		${SC_MEMORY_SRC}
		${SC_KPM_SRC}
		${SC_TOOLS_SRC}
		${SC_COMMON_MODULE_SRC})

add_library(VitebskVillagesModule SHARED ${SOURCES} ${HEADERS})
target_link_libraries(VitebskVillagesModule sc-memory sc-agents-common)

sc_codegen_ex(VitebskVillagesModule ${CMAKE_CURRENT_LIST_DIR} ${CMAKE_CURRENT_LIST_DIR}/generated)

