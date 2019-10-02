---
title: Для необязательных параметров должно быть задано значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: b32c150f0faf4a9dcec3cec7620c3a9c050f6f20
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696875"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>Для необязательных параметров должно быть задано значение по умолчанию
Необязательные параметры должны предоставлять значения по умолчанию, которые можно использовать, если вызывающая процедура не предоставляет параметр.  
  
 **Идентификатор ошибки:** BC30812  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Укажите значения по умолчанию для необязательных параметров. Например:  
  
    ```vb  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>См. также

- [Необязательный](../../../visual-basic/language-reference/modifiers/optional.md)
