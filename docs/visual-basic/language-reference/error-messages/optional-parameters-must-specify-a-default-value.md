---
title: Для необязательных параметров должно быть задано значение по умолчанию
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: dbbcc748a65942e3a89785b267e9231f4a4a01a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686183"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="874ab-102">Для необязательных параметров должно быть задано значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="874ab-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="874ab-103">Необязательные параметры необходимо предоставить значения по умолчанию, которые могут использоваться, если параметр не указан в вызывающей процедуре.</span><span class="sxs-lookup"><span data-stu-id="874ab-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="874ab-104">**Идентификатор ошибки:** BC30812</span><span class="sxs-lookup"><span data-stu-id="874ab-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="874ab-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="874ab-105">To correct this error</span></span>  
  
-   <span data-ttu-id="874ab-106">Указание значений по умолчанию для необязательных параметров; Например:</span><span class="sxs-lookup"><span data-stu-id="874ab-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="874ab-107">См. также</span><span class="sxs-lookup"><span data-stu-id="874ab-107">See also</span></span>
- [<span data-ttu-id="874ab-108">Необязательный</span><span class="sxs-lookup"><span data-stu-id="874ab-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
