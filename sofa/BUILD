cc_binary(
	name = "rpctool",
	srcs = [
		"pbrpc/http-agent/sofa_pbrpc_client.cc"
	],
	deps = [
		":sofa_rpc"
	]
)

cc_library(
	name = "sofa_rpc",
	defs = [
		"_GNU_SOURCE",
		"__STDC_LIMIT_MACROS"
	],	
	srcs = [
		'pbrpc/builtin_service.pb.cc',
		'pbrpc/buffer.cc',
		'pbrpc/dynamic_rpc_channel_impl.cc',
		'pbrpc/timeout_manager_impl.cc',
		'pbrpc/rpc_channel.cc',
		'pbrpc/thread_group.cc',
		'pbrpc/lz4.cc',
		'pbrpc/rpc_option.pb.cc',
		'pbrpc/common.cc',
		'pbrpc/rpc_server.cc',
		'pbrpc/common_internal.cc',
		'pbrpc/mock_test_helper.cc',
		'pbrpc/rpc_server_impl.cc',
		'pbrpc/simple_rpc_channel_impl.cc',
		'pbrpc/rpc_client.cc',
		'pbrpc/rpc_meta.pb.cc',
		'pbrpc/gzip_stream.cc',
		'pbrpc/boost_system_error_code.cc',
		'pbrpc/rpc_error_code.cc',
		'pbrpc/rpc_controller.cc',
		'pbrpc/compressed_stream.cc',
		'pbrpc/timeout_manager.cc',
		'pbrpc/builtin_service_impl.cc',
		'pbrpc/block_wrappers.cc',
		'pbrpc/rpc_endpoint.cc',
		'pbrpc/rpc_client_impl.cc'
	],
	deps = [
		'#z',
		'#rt',
		'//thirdparty/snappy:snappy',
		'//thirdparty/protobuf:protobuf'
	],
        warning = 'no'
)
