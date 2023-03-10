# setpwef


[![PyPI](https://img.shields.io/pypi/v/setpwef)](https://pypi.org/project/setpwef/)
[![GitHub license](https://img.shields.io/github/license/Hyeonji-Ryu/setpwef)](https://github.com/Hyeonji-Ryu/setpwef/blob/main/LICENSE)

setpwef는 set password excel file의 줄임말로 엑셀 파일에 암호를 걸 수 있는 파이썬 패키지입니다. 이 패키지는 Rust 라이브러리를 파이썬에서 사용할 수 있도록 바인딩한 것이며, 사용한 Rust 라이브러리는 [umya-spreadsheet](https://docs.rs/umya-spreadsheet/latest/umya_spreadsheet/) 입니다. 바인딩의 경우 [PyO3](https://docs.rs/pyo3/latest/pyo3/)와 [Maturin](https://docs.rs/maturin/latest/maturin/)을 사용하였습니다.  

setpwef is an abbreviation for set password excel file, which is a Python package that can set a password for an excel file. This package binds the Rust library for use in Python, and the Rust library used is [umya-spreadsheet](https://docs.rs/umya-spreadsheet/latest/umya_spreadsheet/). For binding, [PyO3](https://docs.rs/pyo3/latest/pyo3/) and [Maturin](https://docs.rs/maturin/latest/maturin/) were used.

## How to Use

### 패키지 설치하기

먼저 패키지를 설치합니다.  
you have to install kbodata package first.

```bash
pip install setpwef
```

### 파일 비밀번호 설정하기

엑셀 파일에 비밀번호를 설정합니다.
Set a password for the excel file.

```python
import os
import setpwef

filename = "test.xlsx"
prefix = os.path.join(os.path.dirname(os.path.abspath("test.xlsx")))
path = prefix + "/" + filename
password = "test123"

setpwef.encrypt_excelfile(path, path, password)
```

