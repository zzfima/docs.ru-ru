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
ms.openlocfilehash: 7b926214d3be7f5f57783a8599acf1bb1042f956
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944445"
---
# <a name="error-statement"></a><span data-ttu-id="03933-102">Оператор Error</span><span class="sxs-lookup"><span data-stu-id="03933-102">Error Statement</span></span>
<span data-ttu-id="03933-103">Имитирует возникновение ошибки.</span><span class="sxs-lookup"><span data-stu-id="03933-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03933-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03933-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="03933-105">Части</span><span class="sxs-lookup"><span data-stu-id="03933-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="03933-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="03933-106">Required.</span></span> <span data-ttu-id="03933-107">Может быть любым допустимым номером ошибки.</span><span class="sxs-lookup"><span data-stu-id="03933-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03933-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="03933-108">Remarks</span></span>  
 <span data-ttu-id="03933-109">Эта `Error` инструкция поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="03933-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="03933-110">В новом коде, особенно при создании объектов, используйте `Err` `Raise` метод объекта для создания ошибок времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="03933-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="03933-111">Если `errornumber` определено `Error` , инструкция вызывает обработчик ошибок `Err` после того, как свойства объекта присвоены следующие значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="03933-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="03933-112">Свойство.</span><span class="sxs-lookup"><span data-stu-id="03933-112">Property</span></span>|<span data-ttu-id="03933-113">Значение</span><span class="sxs-lookup"><span data-stu-id="03933-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="03933-114">Значение, указанное в качестве `Error` аргумента инструкции.</span><span class="sxs-lookup"><span data-stu-id="03933-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="03933-115">Может быть любым допустимым номером ошибки.</span><span class="sxs-lookup"><span data-stu-id="03933-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="03933-116">Имя текущего проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="03933-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="03933-117">Строковое выражение, соответствующее возвращаемому значению `Error` функции для указанного `Number`объекта, если эта строка существует.</span><span class="sxs-lookup"><span data-stu-id="03933-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="03933-118">Если строка не существует, `Description` содержит строку нулевой длины ("").</span><span class="sxs-lookup"><span data-stu-id="03933-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="03933-119">Полный диск, путь и имя файла подходящего файла справки Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="03933-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="03933-120">Соответствующий идентификатор контекста файла справки Visual Basic для ошибки, соответствующей `Number` свойству.</span><span class="sxs-lookup"><span data-stu-id="03933-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="03933-121">Нуль.</span><span class="sxs-lookup"><span data-stu-id="03933-121">Zero.</span></span>|  
  
 <span data-ttu-id="03933-122">Если обработчик ошибок не существует или не включен, сообщение об ошибке создается и отображается в `Err` свойствах объекта.</span><span class="sxs-lookup"><span data-stu-id="03933-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03933-123">Некоторые приложения Visual Basic узла не могут создавать объекты.</span><span class="sxs-lookup"><span data-stu-id="03933-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="03933-124">Чтобы определить, может ли он создавать классы и объекты, см. документацию по ведущему приложению.</span><span class="sxs-lookup"><span data-stu-id="03933-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03933-125">Пример</span><span class="sxs-lookup"><span data-stu-id="03933-125">Example</span></span>  
 <span data-ttu-id="03933-126">В этом примере используется `Error` оператор для создания номера ошибки 11.</span><span class="sxs-lookup"><span data-stu-id="03933-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="03933-127">Требования</span><span class="sxs-lookup"><span data-stu-id="03933-127">Requirements</span></span>  
 <span data-ttu-id="03933-128">**Пространство имен:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="03933-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="03933-129">**Сборок** Visual Basic (библиотека времени выполнения, в Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="03933-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03933-130">См. также</span><span class="sxs-lookup"><span data-stu-id="03933-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="03933-131">Оператор On Error</span><span class="sxs-lookup"><span data-stu-id="03933-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="03933-132">Оператор Resume</span><span class="sxs-lookup"><span data-stu-id="03933-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="03933-133">Сообщения об ошибках</span><span class="sxs-lookup"><span data-stu-id="03933-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
