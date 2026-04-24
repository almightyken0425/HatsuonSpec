# 構成元素規格

## 職責範圍

- 每個假名字元可拆解為一或多個構成元素
- 刷題引擎記錄答題結果時，同步更新字元本身及其所有構成元素的答題紀錄
- 供自適應演算法診斷學習者薄弱的認知單位

---

## 元素識別碼定義

| 識別碼 | 代表意義 |
|--------|----------|
| `dakuten` | 濁點 ゛ |
| `handakuten` | 半濁點 ゜ |
| `small_ya` | 小假名 ゃ |
| `small_yu` | 小假名 ゅ |
| `small_yo` | 小假名 ょ |
| `sokuon` | 促音 っ/ッ |
| `choonpu` | 長音符 ー |

- 清音基底假名不使用獨立識別碼，直接以字元 id 表示，例如 か 的識別碼為 `h006`

---

## 字元構成元素規則

`components` 依 `sound_category` 套用以下規則，不逐字列舉：

**清音**

components = 字元自身 id

**濁音**

components = 字元自身 id、對應清音字元 id、`dakuten`

例：が の components = `h047`、`h006`、`dakuten`

**半濁音**

components = 字元自身 id、對應清音字元 id、`handakuten`

例：ぱ の components = `h067`、`h026`、`handakuten`

**拗音 清音系**

components = 字元自身 id、基底清音字元 id、小假名識別碼

例：きゃ の components = `h072`、`h007`、`small_ya`

**拗音 濁音系**

components = 字元自身 id、基底清音字元 id、`dakuten`、小假名識別碼

例：ぎゃ の components = `h093`、`h007`、`dakuten`、`small_ya`

**拗音 半濁音系**

components = 字元自身 id、基底清音字元 id、`handakuten`、小假名識別碼

例：ぴゃ の components = `h102`、`h007`、`handakuten`、`small_ya`

**促音**

components = 字元自身 id、`sokuon`

**長音符**

components = 字元自身 id、`choonpu`
