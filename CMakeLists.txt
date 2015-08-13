PROJECT(readium)
CMAKE_MINIMUM_REQUIRED(VERSION 2.4)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -std=gnu++11 -stdlib=libc++ -include prefix.h -fpermissive -DBUILDING_EPUB3")
SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g -std=gnu11 -stdlib=libc++ -include prefix.h -DBUILDING_EPUB3")

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR} Platform/Linux/include ePub3 ePub3/utilities ePub3/ePub ePub3/ThirdParty/google-url/src)

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
		ePub3/ePub/archive.cpp
		ePub3/ePub/archive_xml.cpp
		ePub3/ePub/cfi.cpp
		ePub3/ePub/container.cpp
		ePub3/ePub/content_handler.cpp
		ePub3/ePub/content_module_manager.cpp
		ePub3/ePub/credential_request.cpp
		ePub3/ePub/encryption.cpp
		ePub3/ePub/epub_collection.cpp
		ePub3/ePub/filter_chain_byte_stream.cpp
		ePub3/ePub/filter_chain_byte_stream_range.cpp
		ePub3/ePub/filter_chain.cpp
		ePub3/ePub/filter_manager.cpp
		ePub3/ePub/filter_manager_impl.cpp
		ePub3/ePub/font_obfuscation.cpp
		ePub3/ePub/glossary.cpp
		ePub3/ePub/initialization.cpp
		ePub3/ePub/library.cpp
		ePub3/ePub/link.cpp
		ePub3/ePub/manifest.cpp
		ePub3/ePub/media-overlays_smil_data.cpp
		ePub3/ePub/media-overlays_smil_model.cpp
		ePub3/ePub/media_support_info.cpp
		ePub3/ePub/nav_point.cpp
		ePub3/ePub/nav_table.cpp
		ePub3/ePub/object_preprocessor.cpp
		ePub3/ePub/package.cpp
		ePub3/ePub/PassThroughFilter.cpp
		ePub3/ePub/property.cpp
		ePub3/ePub/property_extension.cpp
		ePub3/ePub/property_holder.cpp
		ePub3/ePub/signatures.cpp
		ePub3/ePub/spine.cpp
		ePub3/ePub/switch_preprocessor.cpp
		ePub3/ePub/xpath_wrangler.cpp
		ePub3/ePub/zip_archive.cpp
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
		ePub3/ThirdParty/libzip/mkstemp.c                  ePub3/ThirdParty/libzip/zip_get_archive_flag.c
		ePub3/ThirdParty/libzip/zip_add.c                  ePub3/ThirdParty/libzip/zip_get_file_comment.c
		ePub3/ThirdParty/libzip/zip_add_dir.c              ePub3/ThirdParty/libzip/zip_get_name.c
		ePub3/ThirdParty/libzip/zip_close.c                ePub3/ThirdParty/libzip/zip_get_num_files.c
		ePub3/ThirdParty/libzip/zip_delete.c               ePub3/ThirdParty/libzip/zip_memdup.c
		ePub3/ThirdParty/libzip/zip_dirent.c               ePub3/ThirdParty/libzip/zip_name_locate.c
		ePub3/ThirdParty/libzip/zip_entry_free.c           ePub3/ThirdParty/libzip/zip_new.c
		ePub3/ThirdParty/libzip/zip_entry_new.c            ePub3/ThirdParty/libzip/zip_open.c
		ePub3/ThirdParty/libzip/zip_error.c                ePub3/ThirdParty/libzip/zip_rename.c
		ePub3/ThirdParty/libzip/zip_error_clear.c          ePub3/ThirdParty/libzip/zip_replace.c
		ePub3/ThirdParty/libzip/zip_error_get.c            ePub3/ThirdParty/libzip/zip_set_archive_comment.c
		ePub3/ThirdParty/libzip/zip_error_get_sys_type.c   ePub3/ThirdParty/libzip/zip_set_archive_flag.c
		ePub3/ThirdParty/libzip/zip_error_strerror.c       ePub3/ThirdParty/libzip/zip_set_file_comment.c
		ePub3/ThirdParty/libzip/zip_error_to_str.c         ePub3/ThirdParty/libzip/zip_set_name.c
		ePub3/ThirdParty/libzip/zip_err_str.c              ePub3/ThirdParty/libzip/zip_source_buffer.c
		ePub3/ThirdParty/libzip/zip_fclose.c               ePub3/ThirdParty/libzip/zip_source_file.c
		ePub3/ThirdParty/libzip/zip_file_error_clear.c     ePub3/ThirdParty/libzip/zip_source_filep.c
		ePub3/ThirdParty/libzip/zip_file_error_get.c       ePub3/ThirdParty/libzip/zip_source_free.c
		ePub3/ThirdParty/libzip/zip_file_get_offset.c      ePub3/ThirdParty/libzip/zip_source_function.c
		ePub3/ThirdParty/libzip/zip_filerange_crc.c        ePub3/ThirdParty/libzip/zip_source_zip.c
		ePub3/ThirdParty/libzip/zip_file_strerror.c        ePub3/ThirdParty/libzip/zip_stat.c
		ePub3/ThirdParty/libzip/zip_fopen.c                ePub3/ThirdParty/libzip/zip_stat_index.c
		ePub3/ThirdParty/libzip/zip_fopen_index.c          ePub3/ThirdParty/libzip/zip_stat_init.c
		ePub3/ThirdParty/libzip/zip_fread.c                ePub3/ThirdParty/libzip/zip_strerror.c
		ePub3/ThirdParty/libzip/zip_free.c                 ePub3/ThirdParty/libzip/zip_unchange_all.c
		ePub3/ThirdParty/libzip/zip_fseek.c                ePub3/ThirdParty/libzip/zip_unchange_archive.c
		ePub3/ThirdParty/libzip/zip_ftell.c                ePub3/ThirdParty/libzip/zip_unchange.c
		ePub3/ThirdParty/libzip/zip_get_archive_comment.c  ePub3/ThirdParty/libzip/zip_unchange_data.c
		ePub3/utilities/byte_buffer.cpp
		ePub3/utilities/byte_stream.cpp 
		ePub3/utilities/ring_buffer.cpp 
		ePub3/utilities/ref_counted.cpp 
#		ePub3/utilities/run_loop_generic.cpp 
		ePub3/utilities/epub_locale.cpp 
		ePub3/utilities/error_handler.cpp 
		ePub3/utilities/iri.cpp 
		ePub3/utilities/utfstring.cpp 
		ePub3/utilities/path_help.cpp
		ePub3/utilities/future.cpp		)

TARGET_LINK_LIBRARIES(epub3 xml2)

#TARGET_LINK_LIBRARIES()


