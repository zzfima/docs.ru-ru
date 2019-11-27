---
title: Практическое руководство. Вызов процедуры, которая не возвращает значение
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3a5de98c6edf795a11bd9f0465aa6919f09eebfa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340961"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="e149c-102">Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e149c-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="e149c-103">`Sub` процедура не возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="e149c-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="e149c-104">Он вызывается явным образом с помощью изолированного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="e149c-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="e149c-105">Его нельзя вызвать, просто используя его имя в выражении.</span><span class="sxs-lookup"><span data-stu-id="e149c-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="e149c-106">Вызов процедуры подпрограммы</span><span class="sxs-lookup"><span data-stu-id="e149c-106">To call a Sub procedure</span></span>  
  
1. <span data-ttu-id="e149c-107">Укажите имя процедуры `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e149c-107">Specify the name of the `Sub` procedure.</span></span>  
  
2. <span data-ttu-id="e149c-108">Чтобы заключить список аргументов, выполните имя процедуры с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="e149c-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e149c-109">Если аргументы отсутствуют, можно дополнительно опустить круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="e149c-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="e149c-110">Однако использование круглых скобок упрощает чтение кода.</span><span class="sxs-lookup"><span data-stu-id="e149c-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="e149c-111">Поместите аргументы в список аргументов в круглых скобках, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="e149c-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e149c-112">Убедитесь, что аргументы указываются в том же порядке, в котором процедура `Sub` определяет соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e149c-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="e149c-113">В следующем примере вызывается функция Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> для активации окна приложения.</span><span class="sxs-lookup"><span data-stu-id="e149c-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="e149c-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> принимает заголовок окна в качестве единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="e149c-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="e149c-115">Он не возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="e149c-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="e149c-116">Если процесс «Блокнот» не выполняется, в примере создается <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="e149c-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="e149c-117">Процедура `Shell` предполагает, что приложения находятся в указанных путях.</span><span class="sxs-lookup"><span data-stu-id="e149c-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e149c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e149c-118">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="e149c-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="e149c-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e149c-120">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="e149c-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e149c-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="e149c-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e149c-122">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="e149c-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="e149c-123">Практическое руководство. Создание процедуры</span><span class="sxs-lookup"><span data-stu-id="e149c-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="e149c-124">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="e149c-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="e149c-125">Как вызвать обработчик событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e149c-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
