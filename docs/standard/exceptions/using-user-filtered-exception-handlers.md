---
title: Использование обработчиков исключений с пользовательской фильтрацией
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
ms.openlocfilehash: 5537404178b746310f720c5b0c075c77287dda4c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708457"
---
# <a name="using-user-filtered-exception-handlers"></a><span data-ttu-id="3e34d-102">Использование обработчиков исключений с пользовательской фильтрацией</span><span class="sxs-lookup"><span data-stu-id="3e34d-102">Using User-Filtered Exception Handlers</span></span>

<span data-ttu-id="3e34d-103">Сейчас Visual Basic поддерживает исключения с пользовательской фильтрацией.</span><span class="sxs-lookup"><span data-stu-id="3e34d-103">Currently, Visual Basic supports user-filtered exceptions.</span></span> <span data-ttu-id="3e34d-104">Обработчики исключений с пользовательской фильтрацией перехватывают и обрабатывают исключения с учетом определенных для исключения требований.</span><span class="sxs-lookup"><span data-stu-id="3e34d-104">User-filtered exception handlers catch and handle exceptions based on requirements you define for the exception.</span></span> <span data-ttu-id="3e34d-105">Эти обработчики используют инструкцию **Catch** с ключевым словом **When**.</span><span class="sxs-lookup"><span data-stu-id="3e34d-105">These handlers use the **Catch** statement with the **When** keyword.</span></span>  
  
 <span data-ttu-id="3e34d-106">Этот метод удобен, когда конкретный объект исключения соответствует нескольким ошибкам.</span><span class="sxs-lookup"><span data-stu-id="3e34d-106">This technique is useful when a particular exception object corresponds to multiple errors.</span></span> <span data-ttu-id="3e34d-107">В этом случае у объекта обычно есть свойство, которое содержит код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3e34d-107">In this case, the object typically has a property that contains the specific error code associated with the error.</span></span> <span data-ttu-id="3e34d-108">С помощью кода ошибки можно выбрать конкретную ошибку, которую вы хотите обработать в инструкции **Catch**.</span><span class="sxs-lookup"><span data-stu-id="3e34d-108">You can use the error code property in the expression to select only the particular error you want to handle in that **Catch** clause.</span></span>  
  
 <span data-ttu-id="3e34d-109">В следующем примере Visual Basic демонстрируются инструкции **Catch/When**.</span><span class="sxs-lookup"><span data-stu-id="3e34d-109">The following Visual Basic example illustrates the **Catch/When** statement.</span></span>  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 <span data-ttu-id="3e34d-110">Выражение для предложения пользовательской фильтрации не ограничено.</span><span class="sxs-lookup"><span data-stu-id="3e34d-110">The expression of the user-filtered clause is not restricted in any way.</span></span> <span data-ttu-id="3e34d-111">При возникновении исключения в выражении с пользовательской фильтрацией это исключение отбрасывается, а выражение фильтрации считается равным false.</span><span class="sxs-lookup"><span data-stu-id="3e34d-111">If an exception occurs during execution of the user-filtered expression, that exception is discarded and the filter expression is considered to have evaluated to false.</span></span> <span data-ttu-id="3e34d-112">В этом случае среда CLR продолжает поиск обработчика для текущего исключения.</span><span class="sxs-lookup"><span data-stu-id="3e34d-112">In this case, the common language runtime continues the search for a handler for the current exception.</span></span>  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a><span data-ttu-id="3e34d-113">Объединение конкретного исключения и условий пользовательской фильтрации</span><span class="sxs-lookup"><span data-stu-id="3e34d-113">Combining the Specific Exception and the User-Filtered Clauses</span></span>  
 <span data-ttu-id="3e34d-114">Оператор catch может содержать как конкретное исключение, так и условия пользовательской фильтрации.</span><span class="sxs-lookup"><span data-stu-id="3e34d-114">A catch statement can contain both the specific exception and the user-filtered clauses.</span></span> <span data-ttu-id="3e34d-115">Сначала среда выполнения проверяет конкретное исключение.</span><span class="sxs-lookup"><span data-stu-id="3e34d-115">The runtime tests the specific exception first.</span></span> <span data-ttu-id="3e34d-116">Если проверка пройдена, среда выполнения выполняет фильтр пользователя.</span><span class="sxs-lookup"><span data-stu-id="3e34d-116">If the specific exception succeeds, the runtime executes the user filter.</span></span> <span data-ttu-id="3e34d-117">Общий фильтр может содержать ссылку на переменную, объявленную в классе фильтра.</span><span class="sxs-lookup"><span data-stu-id="3e34d-117">The generic filter can contain a reference to the variable declared in the class filter.</span></span> <span data-ttu-id="3e34d-118">Обратите внимание, что порядок двух выражений фильтра изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="3e34d-118">Note that the order of the two filter clauses cannot be reversed.</span></span>  
  
 <span data-ttu-id="3e34d-119">В следующем примере Visual Basic демонстрируется конкретное исключение `ClassLoadException` в инструкции **Catch**, а также предложение для пользовательской фильтрации с использованием ключевого слова **When**.</span><span class="sxs-lookup"><span data-stu-id="3e34d-119">The following Visual Basic example shows the specific exception `ClassLoadException` in the **Catch** statement as well as the user-filtered clause using the **When** keyword.</span></span>  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a><span data-ttu-id="3e34d-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3e34d-120">See also</span></span>

- [<span data-ttu-id="3e34d-121">Исключения</span><span class="sxs-lookup"><span data-stu-id="3e34d-121">Exceptions</span></span>](index.md)
