---
title: Невозможно обратиться к полю <name>, так как оно является членом поля с типизированным значением <name> класса <classname>, базовым классом которого является System.MarshalByRefObject
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: c29d3def2299dc1d7e3b084b3408b3f919addc63
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279593"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="464f5-102">Не может ссылаться на "\<имя >", так как он является членом поля с типизированным значением "\<имя >" класса\<имя_класса > "которого является «System.MarshalByRefObject» как базовый класс</span><span class="sxs-lookup"><span data-stu-id="464f5-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="464f5-103">`System.MarshalByRefObject` Класс позволяет приложения, поддерживающие удаленный доступ к объектам через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="464f5-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="464f5-104">Типы должны быть наследниками `MarshalByRejectObject` класса при использовании типа через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="464f5-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="464f5-105">Состояние объекта не должны копироваться, так как члены объекта не могут использоваться за пределами домена приложения, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="464f5-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="464f5-106">**Идентификатор ошибки:** BC30310</span><span class="sxs-lookup"><span data-stu-id="464f5-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="464f5-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="464f5-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="464f5-108">Проверяет ссылку, чтобы убедиться в том, что член является допустимым.</span><span class="sxs-lookup"><span data-stu-id="464f5-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="464f5-109">Явно укажите элемент с `Me` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="464f5-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464f5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="464f5-110">See also</span></span>
- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="464f5-111">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="464f5-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
