# judgealign

**量化人工裁判与模型裁判的判断一致程度。**

`judgealign` —— 计算两类裁判在同一批样本上的一致率与分歧样本的特征

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`judgealign.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install cry4gender-judgealign
```

装完直接用命令名调用：

```bash
judgealign --help
```

也可以不用安装，直接把 `judgealign.py` 拷走用——它只依赖标准库。

## 为什么需要它

分歧样本单独列出，因为它们才是需要人来看的部分

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测裁判一致性 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python judgealign.py --file input.txt
python judgealign.py --text "示例内容"
python judgealign.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 比例的分母取自你给的口径，不替你选口径。
- 不判断比例高低是否合理。

## 跑测试

```bash
python test_judgealign.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/cry4gender/judgealign>

---

## 关于作者

cry4gender 做评测裁判一致性相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://cry4gender.github.io>
- 仓库：<https://github.com/cry4gender/judgealign>

## 许可

MIT，见 [LICENSE](LICENSE)。
