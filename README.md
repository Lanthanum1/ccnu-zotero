本项目根据 ccnu 附件4：关于修订毕业论文注释与参考文献著录格式的通知.pdf 改写，只适用于理工科本科论文。

arxiv 上获取的论文无法通过格子达检测，优先选择对应发行的期刊或者会议，可以在谷歌学术上搜索，cite-->bibtex，复制之后，在 zotero 中，file-->import from clipboard 即可导入。（如果有对应的发行版则选择对于的发行版，如果没有也可以在谷歌学术选择 arxiv类型的文献，bibtex 会记为 journal。形如：

```latex
@article{zhao2023survey,
  title={A Survey of Large Language Models},
  author={Zhao, Wayne Xin and Zhou, Kun and Li, Junyi and Tang, Tianyi and Wang, Xiaolei and Hou, Yupeng and Min, Yingqian and Zhang, Beichen and Zhang, Junjie and Dong, Zican and others},
  journal={arXiv preprint arXiv:2303.18223},
  year={2023}
}
```

导入之后，执行 linter 插件 [linter](https://zotero-chinese.com/plugins/#search=linter) 获取元信息。（这里可以全选所有文献右键linter，而不必依次点击）

linter 获取的元信息并不全面，可能会缺失年份、出版地、出版社，需要手动填写，见 ./cs-conf.md，这里有计算机类常见的会议出版地和出版社

其中，对于 arxiv 类型，如 Arxiv:2303.18223, Publication 字段会有":"和"." 会导致格子达识别失败，只保留“Arxiv Preprint”即可。volume 字段可以选择点前面的数字如 2303， page可以不填写。

这里需要注意，linter 获取的元信息有时字段本身会包含":"和"."，如 Publication 字段 SORT.Statistics and Operations Research Transactions 会直接导致格子检测为错误格式，因为格子达是根据点号检测的，所有字段最好都不要有":"和"."。

journal 的 page 可以不填写，conference 的 volume 可以不填写。

如果选择不执行 linter，而是手动填写元信息，务必填写language字段为en-US，否则会出现英文文献使用“等”的情况。

每次刷新之后需要全选参考文献，修改段落样式，小四号，首行缩进，1.5倍行距，再运行宏。

添加宏的方式：

视图-->宏-->添加宏-->粘贴 ZoteroLinkCitation.bas-->运行宏

每添加一篇文献，之前的 citation 宏全部失效，最好在最后运行宏。


