---
title: Для необязательных параметров должно быть задано значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 01c0abb366e8605a9b153333e645fc3276b6bd16
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772597"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="92b8c-102">Для необязательных параметров должно быть задано значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="92b8c-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="92b8c-103">Необязательные параметры необходимо предоставить значения по умолчанию, которые могут использоваться, если параметр не указан в вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="92b8c-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="92b8c-104">**Идентификатор ошибки:** BC30812</span><span class="sxs-lookup"><span data-stu-id="92b8c-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92b8c-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="92b8c-105">To correct this error</span></span>  
  
- <span data-ttu-id="92b8c-106">Указание значений по умолчанию для необязательных параметров; Например:</span><span class="sxs-lookup"><span data-stu-id="92b8c-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="92b8c-107">См. также</span><span class="sxs-lookup"><span data-stu-id="92b8c-107">See also</span></span>

- [<span data-ttu-id="92b8c-108">Необязательный</span><span class="sxs-lookup"><span data-stu-id="92b8c-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
