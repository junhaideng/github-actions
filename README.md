# 学学GitHub Actions
```yml
name: GitHub Actions  # 指定Actions的名称
on: [push]  # 触发条件
jobs:  # 需要运行的job，可以有多个
  demo:  # job命令
    runs-on: ubuntu-latest  # 运行环境
    steps: # 运行步骤
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code  # 命令命名
        uses: actions/checkout@v2 
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository  # 命令命名
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."
      - name: use enviroment variables
        env:    
            HOST: 127.0.0.1
        run: echo "host is ${{ HOST }}"
```