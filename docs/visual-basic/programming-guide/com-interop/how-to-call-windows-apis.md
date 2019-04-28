---
title: Практическое руководство. Вызов API Windows (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: e7b76495b83cb9a1dfe7629a1d82695d2046eac2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61818720"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="c0468-102">Практическое руководство. Вызов API Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0468-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="c0468-103">В этом примере определяется и вызывается `MessageBox` функция в библиотеке user32.dll, а затем передается строка.</span><span class="sxs-lookup"><span data-stu-id="c0468-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0468-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c0468-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0468-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c0468-105">Compiling the Code</span></span>  
 <span data-ttu-id="c0468-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="c0468-106">This example requires:</span></span>  
  
- <span data-ttu-id="c0468-107">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="c0468-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c0468-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="c0468-108">Robust Programming</span></span>  
 <span data-ttu-id="c0468-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="c0468-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="c0468-110">Метод не является статическим, является абстрактным или было определено ранее.</span><span class="sxs-lookup"><span data-stu-id="c0468-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="c0468-111">Родительский тип является интерфейсом, или длина *имя* или *dllName* равно нулю.</span><span class="sxs-lookup"><span data-stu-id="c0468-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="c0468-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="c0468-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="c0468-113">*Имя* или *dllName* является `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="c0468-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="c0468-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="c0468-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="c0468-115">Содержащий тип был создан ранее с помощью `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="c0468-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="c0468-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="c0468-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0468-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c0468-117">See also</span></span>

- [<span data-ttu-id="c0468-118">Подробный обзор вызова неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="c0468-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="c0468-119">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="c0468-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="c0468-120">Использование неуправляемых функций DLL</span><span class="sxs-lookup"><span data-stu-id="c0468-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="c0468-121">[Определение метода с помощью отражения порождаемого](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c0468-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="c0468-122">Пошаговое руководство: Вызов API Windows</span><span class="sxs-lookup"><span data-stu-id="c0468-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="c0468-123">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="c0468-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
