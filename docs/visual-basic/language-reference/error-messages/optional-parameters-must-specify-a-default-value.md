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
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="0a8a7-102">Для необязательных параметров должно быть задано значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0a8a7-102">Optional parameters must specify a default value</span></span>

<span data-ttu-id="0a8a7-103">Необязательные параметры должны предоставлять значения по умолчанию, которые можно использовать, если вызывающая процедура не предоставляет параметр.</span><span class="sxs-lookup"><span data-stu-id="0a8a7-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="0a8a7-104">**Идентификатор ошибки:** BC30812</span><span class="sxs-lookup"><span data-stu-id="0a8a7-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="0a8a7-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0a8a7-105">Example</span></span>

<span data-ttu-id="0a8a7-106">Следующий пример приводит к возникновению ошибки BC30812:</span><span class="sxs-lookup"><span data-stu-id="0a8a7-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="0a8a7-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0a8a7-107">To correct this error</span></span>

<span data-ttu-id="0a8a7-108">Укажите значения по умолчанию для необязательных параметров:</span><span class="sxs-lookup"><span data-stu-id="0a8a7-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="0a8a7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0a8a7-109">See also</span></span>

- [<span data-ttu-id="0a8a7-110">Необязательный</span><span class="sxs-lookup"><span data-stu-id="0a8a7-110">Optional</span></span>](../modifiers/optional.md)
