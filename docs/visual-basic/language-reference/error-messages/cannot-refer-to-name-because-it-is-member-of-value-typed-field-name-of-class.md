---
title: Невозможно обратиться к полю <name>, так как оно является членом поля с типизированным значением <name> класса <classname>, базовым классом которого является System.MarshalByRefObject
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: aac190119ced74496c4dd012d200fca6d895ff28
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826773"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="5d2be-102">Не может ссылаться на "\<имя >", так как он является членом поля с типизированным значением "\<имя >" класса\<имя_класса > "которого является «System.MarshalByRefObject» как базовый класс</span><span class="sxs-lookup"><span data-stu-id="5d2be-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="5d2be-103">`System.MarshalByRefObject` Класс позволяет приложения, поддерживающие удаленный доступ к объектам через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="5d2be-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="5d2be-104">Типы должны быть наследниками `MarshalByRejectObject` класса при использовании типа через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="5d2be-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="5d2be-105">Состояние объекта не должны копироваться, так как члены объекта не могут использоваться за пределами домена приложения, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="5d2be-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="5d2be-106">**Идентификатор ошибки:** BC30310</span><span class="sxs-lookup"><span data-stu-id="5d2be-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5d2be-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5d2be-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="5d2be-108">Проверяет ссылку, чтобы убедиться в том, что член является допустимым.</span><span class="sxs-lookup"><span data-stu-id="5d2be-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="5d2be-109">Явно укажите элемент с `Me` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="5d2be-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2be-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5d2be-110">See also</span></span>

- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="5d2be-111">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="5d2be-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
