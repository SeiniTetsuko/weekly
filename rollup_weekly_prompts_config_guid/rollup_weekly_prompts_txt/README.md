逐层上报 Prompt 包（txt guid 版）

用法：
1. 将四个 txt prompt 上传到平台文件系统。
2. 获取各自文件 guid。
3. 填入 config.rollup_global：
   - rollup_trend_prompt_file_guid
   - rollup_final_prompt_file_guid
   - rollup_validation_prompt_file_guid
   - rollup_repair_prompt_file_guid

代码同时兼容将 prompt guid 放在 config 顶层。

dept_id	dept_name	parent_dept_id	dept_level	state_project_guid	state_parent_guid	weekly_target_project_guid	weekly_target_parent_guid	owner_name	owner_guid

{
  "ak": "你的AK",
  "sk": "你的SK",
  "org_guid": "组织GUID",
  "user_guid": "默认执行用户GUID",

  "llm_global": {
    "base_url": "http://agi-gateway.xxx/cloud/v1",
    "api_key": "你的模型API Key",
    "model": "doubao-seed-2.0-pro",
    "temperature": 0.3,
    "max_tokens": 4096,
    "print_stream": false,
    "max_retries": 5
  },

  "rollup_global": {
    "rollup_trend_prompt_file_guid": "父部门趋势分析prompt_txt文件guid",
    "rollup_final_prompt_file_guid": "父部门最终整理prompt_txt文件guid",
    "rollup_validation_prompt_file_guid": "父部门覆盖校验prompt_txt文件guid",
    "rollup_repair_prompt_file_guid": "父部门遗漏修复prompt_txt文件guid",

    "rollup_projects_per_batch": 5,
    "rollup_max_batch_chars": 12000,
    "rollup_tree_max_chars": 2000,

    "rollup_trend_temperature": 0.1,
    "rollup_trend_max_tokens": 4096,

    "rollup_final_temperature": 0.2,
    "rollup_final_max_tokens": 4096,

    "rollup_validation_temperature": 0.0,
    "rollup_validation_max_tokens": 2048,

    "rollup_repair_temperature": 0.1,
    "rollup_repair_max_tokens": 4096,

    "enable_rollup_coverage_check": true,
    "enable_rollup_second_validation": false,

    "batch_number": 10,

    "rollup_empty_platform_as_dept": true
  },

  "rollup_target_dept_ids": [
    "CET"
  ],

  "dept_config_file_guid": "部门配置Excel文件guid",

  "keep_temp_files": false
}