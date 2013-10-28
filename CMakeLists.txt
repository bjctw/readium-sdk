PROJECT(readium)
CMAKE_MINIMUM_REQUIRED(VERSION 2.4)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -stdlib=libc++ -include prefix.h -fpermissive -DBUILDING_EPUB3")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu11 -stdlib=libc++ -include prefix.h -DBUILDING_EPUB3")

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR} Platform/Linux/include/boost Platform/Linux/include ePub3 ePub3/utilities ePub3/ePub ePub3/ThirdParty/google-url/src)

ADD_LIBRARY(epub3 SHARED 
		ePub3/xml/utilities/io.cpp 
		ePub3/xml/validation/schema.cpp 
		ePub3/xml/tree/node.cpp 
		ePub3/xml/tree/xpath.cpp 
		ePub3/xml/validation/ns.cpp 
		ePub3/xml/utilities/base.cpp 
		ePub3/xml/tree/document.cpp 
		ePub3/xml/validation/c14n.cpp 
		ePub3/xml/tree/element.cpp 
		ePub3/ePub/zip_archive.cpp 
		ePub3/ePub/archive.cpp 
		ePub3/ePub/container.cpp 
		ePub3/ePub/package.cpp 
		ePub3/ePub/archive_xml.cpp 
		ePub3/ePub/xpath_wrangler.cpp 
		ePub3/ePub/spine.cpp 
		ePub3/ePub/manifest.cpp 
		ePub3/ePub/cfi.cpp 
		ePub3/ePub/nav_point.cpp 
		ePub3/ePub/nav_table.cpp 
		ePub3/ePub/glossary.cpp 
		ePub3/ePub/library.cpp 
		ePub3/ePub/font_obfuscation.cpp 
		ePub3/ePub/encryption.cpp 
		ePub3/ePub/signatures.cpp 
		ePub3/utilities/iri.cpp 
		ePub3/utilities/utfstring.cpp 
		ePub3/ThirdParty/google-url/base/string16.cc 
		ePub3/ThirdParty/google-url/src/gurl.cc 
		ePub3/ThirdParty/google-url/src/url_canon_etc.cc 
		ePub3/ThirdParty/google-url/src/url_canon_filesystemurl.cc 
		ePub3/ThirdParty/google-url/src/url_canon_fileurl.cc 
		ePub3/ThirdParty/google-url/src/url_canon_host.cc 
		ePub3/ThirdParty/google-url/src/url_canon_internal.cc 
		ePub3/ThirdParty/google-url/src/url_canon_ip.cc 
		ePub3/ThirdParty/google-url/src/url_canon_mailtourl.cc 
		ePub3/ThirdParty/google-url/src/url_canon_path.cc 
		ePub3/ThirdParty/google-url/src/url_canon_pathurl.cc 
		ePub3/ThirdParty/google-url/src/url_canon_query.cc 
		ePub3/ThirdParty/google-url/src/url_canon_relative.cc 
		ePub3/ThirdParty/google-url/src/url_canon_stdurl.cc 
		ePub3/ThirdParty/google-url/src/url_parse.cc 
		ePub3/ThirdParty/google-url/src/url_parse_file.cc 
		ePub3/ThirdParty/google-url/src/url_util.cc 
		ePub3/ThirdParty/google-url/src/url_canon_cpp11.cc 
		ePub3/ThirdParty/google-url/base/logging.cc 
		ePub3/ePub/content_handler.cpp 
		ePub3/ePub/switch_preprocessor.cpp 
		ePub3/ePub/object_preprocessor.cpp 
		ePub3/ePub/media_support_info.cpp 
		ePub3/utilities/byte_stream.cpp 
		ePub3/utilities/ring_buffer.cpp 
		ePub3/utilities/ref_counted.cpp 
		ePub3/utilities/run_loop_generic.cpp 
		ePub3/utilities/epub_locale.cpp 
		ePub3/utilities/error_handler.cpp 
		ePub3/ePub/property_holder.cpp 
		ePub3/ePub/property.cpp 
		ePub3/ePub/property_extension.cpp )


#TARGET_LINK_LIBRARIES()


