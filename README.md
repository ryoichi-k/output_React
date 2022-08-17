# output_React
Reactのアウトプットの場所

※注意：.envファイルを変更した場合は一度サーバーを終了してnpm startで再度立ち上げる必要がある。


## react-router-domインストール

fonrtのreactアプリディレクトリで以下コマンドを叩く
```
npm i react-router-dom
```

package.jsonで確認

```.json
{
  "name": "sns-front",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@emotion/react": "^11.10.0",
    "@emotion/styled": "^11.10.0",
    "@mui/icons-material": "^5.8.4",
    "@mui/material": "^5.10.0",
    "@mui/styled-engine-sc": "^5.10.0",
    "@testing-library/jest-dom": "^5.16.5",
    "@testing-library/react": "^13.3.0",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.3.0",
    "react-scripts": "5.0.1",
    "styled-components": "^5.3.5",
    "web-vitals": "^2.1.4"
  },
```

App.jsでreact-router-domをインポートする。基本的に以下を入れておくとよい。→App.jsでURLによってコンポーネントを切り替えるイメージ
```app.js
import {
    BrowserRouter as Router,
    Route,
    Routes,
    Link,
    Redirect,
    Navigate,
  } from "react-router-dom";
```

```app.js
function App() {
    return(
        <Router>
            <Routes>
                <Route path="/" element={<Home />} />
                <Route path="/login" element={<Login />} />
                <Route path="/register" element={<Register />} />
                <Route path="/profile/:username" element={<Profile />} />
            </Routes>
        </Router>
    )
}
```

## Linkコンポーネントを使っての画面遷移
<Link>コンポーネントのtoで遷移先のURL。styleでcss設定可能。下記例ではリンクの紫色と下線を黒色で下線なしに変更している。
  SNSのロゴを押せばホームに遷移

```app.jsx
import { Link } from 'react-router-dom';


<Link to="/" style={{ textDecoration: "none", color: "black" }}>
   <span className="logo">SNS</span>
</Link>
```

## axios導入
axiosは自作のAPIを叩ける便利なライブラリ。フロント側のフォルダで以下のコマンドでインストールする。
```
npm i axios
```

## useStateについて
const [変数、変数の状態を変更することができる関数] = useState(変数の初期値)

注意：importを忘れないように！

変数likeの値の状況をsetLikeを使って変更できる。

```app.js
import React, { useState } from 'react'

//いいね
const [like, setLike] = useState(post.like)
const [isLiked, setIsLiked] = useState(false)
```
