# GPT Image Playground 原型迁移记录

- 源项目：https://github.com/CookSleep/gpt_image_playground
- 原型目录：`src/prototypes/gpt-image-playground/`
- 迁移范围：保留上游 `src/` 组件、hooks、lib、store、类型、样式、public 资源、README 和 LICENSE，排除测试文件、部署脚本和文档截图。
- 适配方式：新增当前项目要求的 `index.tsx` 入口，保留上游源码在 `source/` 下用于继续编辑。
- 运行假设：图像生成 API 仍按上游设置弹窗配置；本次只负责静态前端原型迁入和预览可用性。
