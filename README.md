# 👋 Welcome!

## Contribution Guideline

```mermaid
flowchart LR

start([Start]) -->
et{Explainer<br/>Medium}

et -->
|Python<br/>Oriented| gc[Create<br/>Google Colab] -->
move[Move to corr<br/>GDrive Folder] -->
share[Ensure GDSC<br/>as owner] -->
coc

et -->
|Others| m[Create .md<br/>in GitHub] -->
seg

content[Finalized<br/>Content] -->
misc1["
1. Add event details
2. Add GMeet link
"] -->
scg & cw

cw[Conduct<br/>Workshop] -->
misc2["
1. Add recording link
2. Remove GMeet link
"] -->
scg & stop([Stop])

subgraph Python Oriented
		gc
		move
		share
		scg[Save copy<br/>in GitHub]
		coc[Collaborate<br/>on Colab]
end

subgraph Others
	m
	seg[Collaborate<br/>on GitHub]
end

con[/Contributors/] -->
|Suggest<br/>Edits| coc & seg -->
|Update| content
```

## ✨ Contributors

<a href="https://github.com/gdscbpdc/gdscbpdc.github.io/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gdscbpdc/gdscbpdc.github.io" loading="lazy" />
</a>

## ⚠️ Disclaimers

If you want to publish this on your own, **make sure to give due credit**, to help support this project :)

## License

https://github.com/gdscbpdc/gdscbpdc.github.io/blob/6994f73a813007bc5ae105b16e4c9e58b64fbd56/license#L1-L21

