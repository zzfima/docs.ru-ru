---
title: Как выполнить Вызов API Windows (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 5db6e299012982024f34d46906de1a3be9b20ff1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650705"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="04d73-102">Как выполнить Вызов API Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04d73-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="04d73-103">В этом примере определяется и вызывается `MessageBox` функция в библиотеке user32.dll, а затем передается строка.</span><span class="sxs-lookup"><span data-stu-id="04d73-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04d73-104">Пример</span><span class="sxs-lookup"><span data-stu-id="04d73-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="04d73-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="04d73-105">Compiling the Code</span></span>  
 <span data-ttu-id="04d73-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="04d73-106">This example requires:</span></span>  
  
-   <span data-ttu-id="04d73-107">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="04d73-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="04d73-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="04d73-108">Robust Programming</span></span>  
 <span data-ttu-id="04d73-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="04d73-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="04d73-110">Метод не является статическим, является абстрактным или было определено ранее.</span><span class="sxs-lookup"><span data-stu-id="04d73-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="04d73-111">Родительский тип является интерфейсом, или длина *имя* или *dllName* равно нулю.</span><span class="sxs-lookup"><span data-stu-id="04d73-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="04d73-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="04d73-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="04d73-113">*Имя* или *dllName* является `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="04d73-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="04d73-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="04d73-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="04d73-115">Содержащий тип был создан ранее с помощью `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="04d73-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="04d73-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="04d73-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d73-117">См. также</span><span class="sxs-lookup"><span data-stu-id="04d73-117">See also</span></span>

- [<span data-ttu-id="04d73-118">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="04d73-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="04d73-119">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="04d73-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="04d73-120">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="04d73-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="04d73-121">Определение метода с помощью отражения порождаемого</span><span class="sxs-lookup"><span data-stu-id="04d73-121">Defining a Method with Reflection Emit</span></span>](https://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)
- [<span data-ttu-id="04d73-122">Пошаговое руководство: Вызов API Windows</span><span class="sxs-lookup"><span data-stu-id="04d73-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="04d73-123">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="04d73-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
