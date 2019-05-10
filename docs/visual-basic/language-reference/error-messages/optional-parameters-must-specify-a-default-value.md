---
title: Для необязательных параметров должно быть задано значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 0f501b518d5b3f2d48ced33885da2afd353c609e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665679"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>Для необязательных параметров должно быть задано значение по умолчанию
Необязательные параметры необходимо предоставить значения по умолчанию, которые могут использоваться, если параметр не указан в вызывающей процедуре.  
  
 **Идентификатор ошибки:** BC30812  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Указание значений по умолчанию для необязательных параметров; Например:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>См. также

- [Необязательный](../../../visual-basic/language-reference/modifiers/optional.md)
