# vega_utils
각종 라이브러리

    * 의존성:
        - python 3.8.10 이상
        - pytz 2021.3 이상
        - python-dateutil 2.8.2 이상
        - psutil 5.8.0 이상
------------------
### 사용법
```
    # install
        $  pip install git+ssh://git@github.com/jinland-bommaru/vega_utils.git

    # file logger 사용 시
        from vega_utils import FileLogger, FileLoggerError, LogLevel
                :
                :
        log = FileLogger(
            log_path="./log/",
            log_file="test.log",
            log_level = LogLevel.DEBUG,
            log_compress=True
        )
                :
        # log 생성
        log.debug('this is a test log. time[%s]', time.time())
                :
    # socket logger 사용 시
        from vega_utils import SocketLogger, SocketLoggerError, LogLevel
                :
                :
        log = SocketLogger(
            log_host="localhost",
            log_port=5000,
            log_level = LogLevel.DEBUG
            service_name='stree'
        )
                :
        # log 생성
        log.debug('this is a test log. time[%s]', time.time())

    # ProcessHandle 사용 시
        from vega_utils import ProcessHandle as ph
                :
                :
        result = ph.pids()

    # NetworkHandle 사용 시
        from vega_utils import NetworkHandle as nh
                :
                :
        result = nh.is_url()

    # StringHandle 사용 시
        from vega_utils import StringHandle as sh
                :
                :
        result = sh.emoji(value)

    # DateHandle 사용 시
        from vega_utils import DateHandle as dh
                :
                :
        result = dh.now()
```