## 创建导航
## 修改导航图
## 导航图属性
## 修改起始页
1. /res/navigation/xxx.xml中，关闭 app:startDestination 属性
2. act的oncreate中，加入动态判断代码：
```

when (projectType)) {
            0 -> {//图书馆项目，启动测温页
                LogUtils.d(TAG, "预约通用项目")
                var navHostFragment: NavHostFragment =
                    supportFragmentManager.findFragmentById(R.id.fragment_container) as NavHostFragment//找到容器
                val navGraph =
                    navHostFragment.navController.navInflater.inflate(R.navigation.nav_base)//绑定nav布局
                navGraph.startDestination = R.id.temp_main//设置启动页
                navHostFragment.navController.graph = navGraph  //启动
            }
            1 -> {// 
                LogUtils.d(TAG, "核酸项目")
                var navHostFragment: NavHostFragment =
                    supportFragmentManager.findFragmentById(R.id.fragment_container) as NavHostFragment//找到容器
                val navGraph =
                    navHostFragment.navController.navInflater.inflate(R.navigation.nav_base)//绑定nav布局
                navGraph.startDestination = R.id.card_main//设置启动页
                navHostFragment.navController.graph = navGraph  //启动
            }
            2 -> {// 
                LogUtils.d(TAG, "医院流调表项目")
            }
        }


```
## 动态导航
## 全局导航