---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005279"
---
# <a name="-quiet"></a>-quiet

Запрещает компилятору показывать код синтаксических ошибок и предупреждений.

## <a name="syntax"></a>Синтаксис

```console
-quiet
```

## <a name="remarks"></a>Примечания

По умолчанию `-quiet` не действует. Когда компилятор сообщает об ошибке или предупреждении, связанных с синтаксисом, он также выводит строку из исходного кода. Для приложений, которые анализируют выходные данные компилятора, может быть удобнее, чтобы компилятор выводит только текст диагностической информации.

В следующем примере `Module1` выводит ошибку, которая включает исходный код при компиляции без `-quiet`.

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

Результат

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

При компиляции с `-quiet` компилятор выводит только следующее:

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> Параметр `-quiet` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.

## <a name="example"></a>Пример

Следующий код компилирует `T2.vb` и не отображает код для диагностики компилятора, связанного с синтаксисом:

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
