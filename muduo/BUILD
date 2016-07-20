cc_library(
    name = 'muduo_base',
    srcs = [
        'base/AsyncLogging.cc',
        'base/Condition.cc',
        'base/CountDownLatch.cc',
        'base/Date.cc',
        'base/Exception.cc',
        'base/FileUtil.cc',
        'base/LogFile.cc',
        'base/Logging.cc',
        'base/LogStream.cc',
        'base/ProcessInfo.cc',
        'base/Timestamp.cc',
        'base/TimeZone.cc',
        'base/Thread.cc',
        'base/ThreadPool.cc'
    ],
    deps = [
        '#pthread',
        '#rt'
    ],
    extra_cppflags = [
        '-DCHECK_PTHREAD_RETURN_VALUE',
        '-rdynamic'
    ],
    warning = 'no'
)

cc_library(
    name = 'muduo_net',
    srcs = [
        'net/Acceptor.cc',
        'net/Buffer.cc',
        'net/Channel.cc',
        'net/Connector.cc',
        'net/EventLoop.cc',
        'net/EventLoopThread.cc',
        'net/EventLoopThreadPool.cc',
        'net/InetAddress.cc',
        'net/Poller.cc',
        'net/poller/DefaultPoller.cc',
        'net/poller/EPollPoller.cc',
        'net/poller/PollPoller.cc',
        'net/Socket.cc',
        'net/SocketsOps.cc',
        'net/TcpClient.cc',
        'net/TcpConnection.cc',
        'net/TcpServer.cc',
        'net/Timer.cc',
        'net/TimerQueue.cc',
    ],
    deps = [
        ':muduo_base',
    ],
    warning = 'no'
)

cc_library(
    name = 'muduo_http',
    srcs = [
        'net/http/HttpServer.cc',
        'net/http/HttpResponse.cc'
    ],
    deps = [
        ':muduo_net'
    ]
)

cc_library(
    name = 'muduo_inspect',
    srcs = [
        'net/inspect/Inspector.cc',
        'net/inspect/ProcessInspector.cc',
        'net/inspect/PerformanceInspector.cc',
        'net/inspect/SystemInspector.cc'
    ],
    deps = [
        ':muduo_http',
        '//thirdparty/perftools:tcmalloc_and_profiler'
    ],
    defs = [
        'HAVE_TCMALLOC'
    ]
)

proto_library(
    name = 'muduo_proto',
    srcs = 'net/protorpc/rpc.proto',
)

cc_library(
    name = 'muduo_protobuf_codec',
    srcs = [
        'net/protobuf/ProtobufCodecLite.cc'
    ],
    deps = [
        '//thirdparty/protobuf:protobuf',
        ":muduo_net"
    ]
)

cc_library(
    name = 'muduo_protorpc',
    srcs = [
        'net/protorpc/RpcCodec.cc',
        'net/protorpc/RpcChannel.cc',
        'net/protorpc/RpcServer.cc',
    ],
    deps = [
        ':muduo_net',
        ':muduo_proto',
        ':muduo_protobuf_codec',
        '//thirdparty/protobuf:protobuf',
        '#z'
    ]
)
