---
title: Для необязательных параметров должно быть задано значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: eb782b2fa1fb73c7407b57a0942e5eebb30474ff
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040929"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>Для необязательных параметров должно быть задано значение по умолчанию

Необязательные параметры должны предоставлять значения по умолчанию, которые можно использовать, если вызывающая процедура не предоставляет параметр.

**Идентификатор ошибки:** BC30812

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки BC30812:

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a>Исправление ошибки

Укажите значения по умолчанию для необязательных параметров:

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a>См. также

- [Необязательный](../modifiers/optional.md)
