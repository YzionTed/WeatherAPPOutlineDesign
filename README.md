##APP概要设计

###APP架构模式

采用3层框架结构 视图-控制-模型

####视图层 View

已XML布局，自定义视图，系统控件支持视图层数据显示，例如：开发自定义ChartView显示统计图数据

####控制层 Activity Controller

根据业务逻辑和用户视图的交互，绑定数据到视图层，例如：WeatherActivity中对视图和数据的控制

####模型层 Model Database

数据持久化和数据实体，例如：WeatherDataLoader WeatherDBManager

###封装天气数据接口

根据天气数据服务器API封装一套通用的SDK，用于天气数据查询

###自定义天气动画效果

采用序列帧动画

###抽象天气实体

* Alerts 天气预警
* AQI 空气质量
* Forecast 6天天气数据预报
* Index 指数
* IndexDetail 指数详情
* RealTime 实时天气
 
###天气类型分类

	/**
     * 晴
     */
    public static final int SUNNY = 0;// 晴

    /**
     * 多云
     */
    public static final int CLOUDY = 1;// 多云

    /**
     * 阴
     */
    public static final int OVERCAST = 2;// 阴

    /**
     * 雾
     */
    public static final int FOGGY = 3;// 雾

    /**
     * 特大暴雨
     */
    public static final int SEVERE_STORM = 4;// 特大暴雨

    /**
     * 大暴风雨
     */
    public static final int HEAVY_STORM = 5;// 大暴风雨

    /**
     * 暴风雨
     */
    public static final int STORM = 6;// 暴风雨

    /**
     * 雷阵雨
     */
    public static final int THUNDERSHOWER = 7;// 雷阵雨

    /**
     * 阵雨
     */
    public static final int SHOWER = 8;// 阵雨

    /**
     * 大雨
     */
    public static final int HEAVY_RAIN = 9;// 大雨

    /**
     * 中雨
     */
    public static final int MODERATE_RAIN = 10;// 中雨

    /**
     * 小雨
     */
    public static final int LIGHT_RAIN = 11;// 小雨

    /**
     * 雨夹雪
     */
    public static final int SLEET = 12;// 雨夹雪

    /**
     * 暴雪
     */
    public static final int SNOWSTORM = 13;// 暴雪

    /**
     * 阵雪
     */
    public static final int SNOW_SHOWER = 14;// 阵雪

    /**
     * 大雪
     */
    public static final int HEAVY_SNOW = 15;// 大雪
    /**
     * 中雪
     */
    public static final int MODERATE_SNOW = 16;// 中雪
    /**
     * 小雪
     */
    public static final int LIGHT_SNOW = 17;// 小雪
    /**
     * 强沙尘暴
     */
    public static final int STRONGSANDSTORM = 18;// 强沙尘暴
    /**
     * 沙尘暴
     */
    public static final int SANDSTORM = 19;// 沙尘暴
    /**
     * 沙尘
     */
    public static final int SAND = 20;// 沙尘
    /**
     * 扬沙
     */
    public static final int BLOWING_SAND = 21;// 风沙
    /**
     * 冰雹
     */
    public static final int ICE_RAIN = 22;// 冻雨
    /**
     * 浮尘
     */
    public static final int DUST = 23;// 尘土
    /**
     * 霾
     */
    public static final int HAZE = 24;// 霾
    
###天气预警分类

	if (string.contains("台风蓝色预警")) {
			return R.drawable.dw11;
		} else if (string.contains("台风黄色预警")) {
			return R.drawable.dw12;
		} else if (string.contains("台风橙色预警")) {
			return R.drawable.dw13;
		} else if (string.contains("台风红色预警")) {
			return R.drawable.dw14;
		}
		// ------
		else if (string.contains("暴雨蓝色预警")) {
			return R.drawable.dw21;
		} else if (string.contains("暴雨黄色预警")) {
			return R.drawable.dw22;
		} else if (string.contains("暴雨橙色预警")) {
			return R.drawable.dw23;
		} else if (string.contains("暴雨红色预警")) {
			return R.drawable.dw24;
		}
		// ------
		else if (string.contains("暴雪蓝色预警")) {
			return R.drawable.dw31;
		} else if (string.contains("暴雪黄色预警")) {
			return R.drawable.dw32;
		} else if (string.contains("暴雪橙色预警")) {
			return R.drawable.dw33;
		} else if (string.contains("暴雪红色预警")) {
			return R.drawable.dw34;
		}
		// ------
		else if (string.contains("寒潮蓝色预警")) {
			return R.drawable.dw41;
		} else if (string.contains("寒潮黄色预警")) {
			return R.drawable.dw42;
		} else if (string.contains("寒潮橙色预警")) {
			return R.drawable.dw43;
		} else if (string.contains("寒潮红色预警")) {
			return R.drawable.dw44;
		}
		// ------
		else if (string.contains("大风蓝色预警")) {
			return R.drawable.dw51;
		} else if (string.contains("大风黄色预警")) {
			return R.drawable.dw52;
		} else if (string.contains("大风橙色预警")) {
			return R.drawable.dw53;
		} else if (string.contains("大风红色预警")) {
			return R.drawable.dw54;
		}
		// ------
		else if (string.contains("沙尘暴蓝色预警")) {
			return R.drawable.dw61;
		} else if (string.contains("沙尘暴黄色预警")) {
			return R.drawable.dw62;
		} else if (string.contains("沙尘暴橙色预警")) {
			return R.drawable.dw63;
		} else if (string.contains("沙尘暴红色预警")) {
			return R.drawable.dw64;
		}
		// ------
		else if (string.contains("高温蓝色预警")) {
			return R.drawable.dw71;
		} else if (string.contains("高温黄色预警")) {
			return R.drawable.dw72;
		} else if (string.contains("高温橙色预警")) {
			return R.drawable.dw73;
		} else if (string.contains("高温红色预警")) {
			return R.drawable.dw74;
		}
		// ------
		else if (string.contains("高温蓝色预警")) {
			return R.drawable.dw71;
		} else if (string.contains("高温黄色预警")) {
			return R.drawable.dw72;
		} else if (string.contains("高温橙色预警")) {
			return R.drawable.dw73;
		} else if (string.contains("高温红色预警")) {
			return R.drawable.dw74;
		}
		// ------
		else if (string.contains("干旱蓝色预警")) {
			return R.drawable.dw81;
		} else if (string.contains("干旱黄色预警")) {
			return R.drawable.dw82;
		} else if (string.contains("干旱橙色预警")) {
			return R.drawable.dw83;
		} else if (string.contains("干旱红色预警")) {
			return R.drawable.dw84;
		}
		// ------
		else if (string.contains("雷电蓝色预警")) {
			return R.drawable.dw91;
		} else if (string.contains("雷电黄色预警")) {
			return R.drawable.dw92;
		} else if (string.contains("雷电橙色预警")) {
			return R.drawable.dw93;
		} else if (string.contains("雷电红色预警")) {
			return R.drawable.dw94;
		}
		// ------
		else if (string.contains("冰雹蓝色预警")) {
			return R.drawable.dw101;
		} else if (string.contains("冰雹黄色预警")) {
			return R.drawable.dw102;
		} else if (string.contains("冰雹橙色预警")) {
			return R.drawable.dw103;
		} else if (string.contains("冰雹红色预警")) {
			return R.drawable.dw104;
		}
		// ------
		else if (string.contains("霜冻蓝色预警")) {
			return R.drawable.dw111;
		} else if (string.contains("霜冻黄色预警")) {
			return R.drawable.dw112;
		} else if (string.contains("霜冻橙色预警")) {
			return R.drawable.dw113;
		} else if (string.contains("霜冻红色预警")) {
			return R.drawable.dw114;
		}
		// ------
		else if (string.contains("大雾蓝色预警")) {
			return R.drawable.dw121;
		} else if (string.contains("大雾黄色预警")) {
			return R.drawable.dw122;
		} else if (string.contains("大雾橙色预警")) {
			return R.drawable.dw123;
		} else if (string.contains("大雾红色预警")) {
			return R.drawable.dw124;
		}
		// ------
		else if (string.contains("霾蓝色预警")) {
			return R.drawable.dw131;
		} else if (string.contains("霾黄色预警")) {
			return R.drawable.dw132;
		} else if (string.contains("霾橙色预警")) {
			return R.drawable.dw133;
		} else if (string.contains("霾红色预警")) {
			return R.drawable.dw134;
		}
		// ------
		else if (string.contains("道路结冰蓝色预警信号")) {
			return R.drawable.dw141;
		} else if (string.contains("道路结冰黄色预警信号")) {
			return R.drawable.dw142;
		} else if (string.contains("道路结冰橙色预警信号")) {
			return R.drawable.dw143;
		} else if (string.contains("道路结冰红色预警信号")) {
			return R.drawable.dw144;
		}
		
###使用第三方库

* AsynchHttpClient 网络请求库
* UniversalImageLoader 图片加载
* avoscloud 云服务平台
* avospush 消息推送服务平台
* BaiduMapSDK 百度地图，卫星定位 
* nineoldandroids 动画库

###全国城市数据库

采用本地CityDatabase.db作为城市查询，亦可通过城市查询API查询城市ID

###图片视频语音上传

使用AsynchHttpClient 网络请求库，服务器接口需要支持多媒体内容传输，可支持大文件上传，实时更新传输进度

###消息推送

采用 https://leancloud.cn/ 的推送服务，把sdk集成进app中

###地图

采用百度开放平台的地图服务，使用百度地图API在地图上进行绘制图标和位置点，路劲规划等

###统计图

采用Android Chart Tools库提供的强大统计图计算和展示功能


