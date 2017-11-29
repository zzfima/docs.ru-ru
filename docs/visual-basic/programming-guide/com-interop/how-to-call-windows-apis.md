---
title: "Практическое руководство. Вызов Windows API (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a219e031cdd36c713db8dcee6cc1da3849c9cf93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="79d0f-102">Практическое руководство. Вызов Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79d0f-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="79d0f-103">В этом примере определяется и вызывается `MessageBox` функции в библиотеке user32.dll и передает строку.</span><span class="sxs-lookup"><span data-stu-id="79d0f-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79d0f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="79d0f-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="79d0f-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="79d0f-105">Compiling the Code</span></span>  
 <span data-ttu-id="79d0f-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="79d0f-106">This example requires:</span></span>  
  
-   <span data-ttu-id="79d0f-107">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="79d0f-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="79d0f-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="79d0f-108">Robust Programming</span></span>  
 <span data-ttu-id="79d0f-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="79d0f-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="79d0f-110">Метод не является статическим, является абстрактным или было определено ранее.</span><span class="sxs-lookup"><span data-stu-id="79d0f-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="79d0f-111">Родительский тип является интерфейсом или длина *имя* или *dllName* равно нулю.</span><span class="sxs-lookup"><span data-stu-id="79d0f-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="79d0f-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="79d0f-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="79d0f-113">*Имя* или *dllName* — `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="79d0f-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="79d0f-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="79d0f-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="79d0f-115">Содержащий тип был создан ранее с помощью `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="79d0f-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="79d0f-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="79d0f-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d0f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="79d0f-117">See Also</span></span>  
 [<span data-ttu-id="79d0f-118">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="79d0f-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="79d0f-119">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="79d0f-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="79d0f-120">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="79d0f-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="79d0f-121">Определение метода с отражением выпуска</span><span class="sxs-lookup"><span data-stu-id="79d0f-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/en-us/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="79d0f-122">Пошаговое руководство. Вызов API-интерфейсов Windows</span><span class="sxs-lookup"><span data-stu-id="79d0f-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="79d0f-123">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="79d0f-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
