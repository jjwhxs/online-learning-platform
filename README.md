### 系统介绍

基于SpringBoot和Vue实现的在线学习平台采用前后端分离的架构方式，前台系统实现了用户注册/登录、首页、课程、教师、我的课程、我的错题集、我的文章、我的收藏、问卷、浏览记录、系统公告、搜索等功能模块，后台系统实现了系统首页、公告管理、课程管理、章节管理、作业管理、学生管理、教师管理、管理员管理、文章审核、分组管理、问卷管理、文章分类管理、班级管理、个人设置等功能模块。

### 技术选型

开发工具：idea2020.3+Webstorm2020.3

运行环境：jdk1.8+maven3.6.0+MySQL5.7+nodejs14.21.3

服务端技术：Springboot+Mybatis-Plus+SpringSecurity+Fastjson

前端技术：html+css+Vue+axios+Element-UI+echarts

### 成果展示

用户登录
<img width="1920" height="990" alt="用户登录" src="https://github.com/user-attachments/assets/149a33be-13a0-42b2-a3f4-c56dd1369cdf" />

前台系统->首页
<img width="1920" height="990" alt="前台系统-首页" src="https://github.com/user-attachments/assets/971c49a3-d023-4933-9312-4f09ac5a9ae3" />

前台系统->课程
<img width="1920" height="990" alt="前台系统-课程" src="https://github.com/user-attachments/assets/0829f8a3-24a4-4540-b59e-4c26205cebff" />

前台系统->教师
<img width="1920" height="990" alt="前台系统-教师" src="https://github.com/user-attachments/assets/b0e8bc95-24f7-4e1d-aafb-33988f141f21" />

前台系统->我的课程
<img width="1920" height="990" alt="前台系统-我的课程" src="https://github.com/user-attachments/assets/097ce738-91cc-4824-b168-5d07b9197008" />

前台系统->我的错题集
<img width="1920" height="990" alt="前台系统-我的错题集" src="https://github.com/user-attachments/assets/cd964f2c-e2d3-4575-8909-a4e7f0fb30d3" />

前台系统->我的文章
<img width="1920" height="990" alt="前台系统-我的文章" src="https://github.com/user-attachments/assets/e1172747-c9a4-45be-91b8-494a808e2cdc" />

前台系统->我的收藏
<img width="1920" height="990" alt="前台系统-我的收藏" src="https://github.com/user-attachments/assets/8830ba4d-2efc-4398-a964-d3a3d5e7eba2" />

前台系统->问卷
<img width="1920" height="990" alt="前台系统-问卷" src="https://github.com/user-attachments/assets/e545c33d-9560-4565-bef3-a71297ac68ae" />

前台系统->浏览记录
<img width="1920" height="990" alt="前台系统-浏览记录" src="https://github.com/user-attachments/assets/82594515-fd6b-4660-b5ca-49da3d98a17a" />

后台系统->系统首页
<img width="1920" height="990" alt="后台系统-系统首页" src="https://github.com/user-attachments/assets/50876a24-2503-42b1-91c6-6596fe151c38" />

后台系统->公告管理
<img width="1920" height="990" alt="后台系统-公告管理" src="https://github.com/user-attachments/assets/c7deae98-859c-4037-9172-b41c0a0706fd" />

后台系统->课程管理
<img width="1920" height="990" alt="后台系统-课程管理" src="https://github.com/user-attachments/assets/4e82d4f8-2acb-4fc9-a27e-38124ee3dc77" />

后台系统->章节管理
<img width="1920" height="990" alt="后台系统-章节管理" src="https://github.com/user-attachments/assets/7a18bfa3-40ea-45fb-a143-62341c62b73a" />

后台系统->作业管理
<img width="1920" height="990" alt="后台系统-作业管理" src="https://github.com/user-attachments/assets/650b1afe-1bad-4610-80db-6d74e0743736" />

后台系统->学生管理
<img width="1920" height="990" alt="后台系统-学生管理" src="https://github.com/user-attachments/assets/d5dadbf8-015b-4ff9-9e29-0d549619da16" />

后台系统->教师管理
<img width="1920" height="990" alt="后台系统-教师管理" src="https://github.com/user-attachments/assets/dc616fee-cd58-4ebc-b2e6-a91737eb672c" />

后台系统->文章审核
<img width="1920" height="990" alt="后台系统-文章审核" src="https://github.com/user-attachments/assets/49c6747a-ce55-497e-9a3d-e91c0f62f3f3" />

后台系统->分组管理
<img width="1920" height="990" alt="后台系统-分组管理" src="https://github.com/user-attachments/assets/a0469895-1892-4670-bf13-2d7512a41c7f" />

后台系统->问卷管理
<img width="1920" height="990" alt="后台系统-问卷管理" src="https://github.com/user-attachments/assets/bb45577c-aeae-49f5-9be9-5e9a9bb7a5a2" />

后台系统->文章分类管理
<img width="1920" height="990" alt="后台系统-文章分类管理" src="https://github.com/user-attachments/assets/972a8cfc-859d-4e3e-b8ae-0f9478fe64cb" />

后台系统->班级管理
<img width="1920" height="990" alt="后台系统-班级管理" src="https://github.com/user-attachments/assets/9b1202c5-df11-492f-b548-df99e9bb3fa7" />

### 源码展示
@RestController

@RequestMapping("/question")

public class QuestionController {

@Autowired

private QuestionService questionService;

@Autowired

private UserService userService;

@PostMapping("findPage")

public Result findPage(Question question) {

    String userId = JwtUtil.getUserId();
    User user = userService.getById(userId);
    if (user != null && user.getType() == 1) {
        question.setTeacherId(user.getId());
    }
    Page<Question> page = questionService.findPage(question);
    return Result.success(page);
    
}

@PostMapping("findList")

public Result findList(Question question) {

    QueryWrapper<Question> queryWrapper = new QueryWrapper<>();
    queryWrapper.lambda().eq(StringUtils.isNotBlank(question.getTaskId()),Question::getTaskId,question.getTaskId());
    List<Question> list = questionService.list(queryWrapper);
    return Result.success(list);
    
}

@PostMapping("add")

public Result add(Question question) {

    String userId = JwtUtil.getUserId();
    User user = userService.getById(userId);
    question.setStudentId(user.getId());
    boolean save = questionService.save(question);
    if (save) {
        return Result.success();
    } else {
        return Result.fail();
    }
    
}

@PostMapping("update")

public Result update(Question question) {

    boolean update = questionService.updateById(question);
    if (update) {
        return Result.success("修改成功");
    } else {
        return Result.fail("修改失败");
    }
    
}

@GetMapping("/delete")

@Transactional(rollbackFor = Exception.class)

public Result delete(@RequestParam("id") String id) {

    boolean remove = questionService.removeById(id);
    if (remove) {
        return Result.success("删除成功");
    } else {
        return Result.fail("删除失败");
    }
    
}

}

### 账号地址及其它说明

1、地址说明

前台系统：localhost:8080

后台系统：localhost:8080/admin/

2、账号说明

学生：zhangsan/123456

老师：wangjiao/123456

管理员：admin/123456

3、目录结构展示

<img width="980" height="177" alt="目录结构展示" src="https://github.com/user-attachments/assets/3afa6356-f8a8-4fc4-a0cf-859e4769c9d8" />

4、项目结构展示

<img width="1730" height="819" alt="项目结构展示" src="https://github.com/user-attachments/assets/97dfe3c3-cf77-4d88-aa4e-d62b7c9eb5d4" />

5、运行步骤

1）创建数据库、导入sql脚本

2）修改application.properties中的数据库配置文件，启动服务端

3）在learn-manage目录下打开cmd，执行npm install或者yarn install下载依赖

4）下载完毕后启动前端npm run serve，访问端口

获取方式(可远程调试)
访问链接(在浏览器中手动输入下图中的地址)：

<img width="1054" height="115" alt="链接" src="https://github.com/user-attachments/assets/9b3cde54-91d0-4bd5-ae9e-f023fe6f440c" />

若资源获取失败，可添加happy35596339(vx)或2061772307(qq)进行交流
