---
title: Оператор Error (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 8ac7cee2f9959bc75df165d00d3a0a67e1dd9af0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58837537"
---
# <a name="error-statement"></a><span data-ttu-id="b6c18-102">Оператор Error</span><span class="sxs-lookup"><span data-stu-id="b6c18-102">Error Statement</span></span>
<span data-ttu-id="b6c18-103">Имитирует возникновение ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6c18-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6c18-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="b6c18-105">Части</span><span class="sxs-lookup"><span data-stu-id="b6c18-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="b6c18-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b6c18-106">Required.</span></span> <span data-ttu-id="b6c18-107">Может быть любой допустимый номер ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6c18-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6c18-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6c18-108">Remarks</span></span>  
 <span data-ttu-id="b6c18-109">`Error` Инструкция поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="b6c18-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="b6c18-110">В новом коде, особенно в том случае, при создании объектов, используйте `Err` объекта `Raise` метод для создания ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6c18-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="b6c18-111">Если `errornumber` определен, `Error` инструкция вызывает обработчик ошибок после свойства `Err` объекта назначаются следующие значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b6c18-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="b6c18-112">Свойство</span><span class="sxs-lookup"><span data-stu-id="b6c18-112">Property</span></span>|<span data-ttu-id="b6c18-113">Значение</span><span class="sxs-lookup"><span data-stu-id="b6c18-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="b6c18-114">Значение, указанное в качестве аргумента `Error` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b6c18-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="b6c18-115">Может быть любой допустимый номер ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6c18-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="b6c18-116">Имя текущего проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b6c18-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="b6c18-117">Строковое выражение, соответствующее возвращаемое значение `Error` функция для указанного `Number`, если эта строка существует.</span><span class="sxs-lookup"><span data-stu-id="b6c18-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="b6c18-118">Если строка не существует, `Description` содержит строку нулевой длины (»»).</span><span class="sxs-lookup"><span data-stu-id="b6c18-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="b6c18-119">Полное имя диска, путь и имя файла, соответствующего файла справки Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b6c18-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="b6c18-120">Соответствующий Visual Basic файла справки идентификатор контекста для ошибки, соответствующий `Number` свойство.</span><span class="sxs-lookup"><span data-stu-id="b6c18-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="b6c18-121">Ноль.</span><span class="sxs-lookup"><span data-stu-id="b6c18-121">Zero.</span></span>|  
  
 <span data-ttu-id="b6c18-122">Если обработчик ошибок отсутствует или отключен, сообщение об ошибке создаются и отображаются из `Err` свойства объекта.</span><span class="sxs-lookup"><span data-stu-id="b6c18-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6c18-123">Некоторые хост-приложения Visual Basic нельзя создавать объекты.</span><span class="sxs-lookup"><span data-stu-id="b6c18-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="b6c18-124">См. в разделе документации ведущего приложения для определения возможности создания классов и объектов.</span><span class="sxs-lookup"><span data-stu-id="b6c18-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6c18-125">Пример</span><span class="sxs-lookup"><span data-stu-id="b6c18-125">Example</span></span>  
 <span data-ttu-id="b6c18-126">В этом примере используется `Error` инструкции для создания ошибки номер 11.</span><span class="sxs-lookup"><span data-stu-id="b6c18-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="b6c18-127">Требования</span><span class="sxs-lookup"><span data-stu-id="b6c18-127">Requirements</span></span>  
 <span data-ttu-id="b6c18-128">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="b6c18-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="b6c18-129">**Сборка:** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="b6c18-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c18-130">См. также</span><span class="sxs-lookup"><span data-stu-id="b6c18-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="b6c18-131">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="b6c18-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="b6c18-132">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="b6c18-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="b6c18-133">Сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="b6c18-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
