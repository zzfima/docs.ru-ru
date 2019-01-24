---
title: Не может ссылаться на &#39; &lt;имя&gt; &#39; так как он является членом поля с типизированным значением &#39; &lt;имя&gt; &#39; класса &#39; &lt;classname&gt; &#39;с &#39;System.MarshalByRefObject&#39; как базовый класс
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: a6298c3e0f5102397d5cc3f237a186598c6b5ecc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739301"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="39a3d-102">Не может ссылаться на &#39; &lt;имя&gt; &#39; так как он является членом поля с типизированным значением &#39; &lt;имя&gt; &#39; класса &#39; &lt;classname&gt; &#39;с &#39;System.MarshalByRefObject&#39; как базовый класс</span><span class="sxs-lookup"><span data-stu-id="39a3d-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="39a3d-103">`System.MarshalByRefObject` Класс позволяет приложения, поддерживающие удаленный доступ к объектам через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="39a3d-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="39a3d-104">Типы должны быть наследниками `MarshalByRejectObject` класса при использовании типа через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="39a3d-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="39a3d-105">Состояние объекта не должны копироваться, так как члены объекта не могут использоваться за пределами домена приложения, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="39a3d-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="39a3d-106">**Идентификатор ошибки:** BC30310</span><span class="sxs-lookup"><span data-stu-id="39a3d-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="39a3d-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="39a3d-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="39a3d-108">Проверяет ссылку, чтобы убедиться в том, что член является допустимым.</span><span class="sxs-lookup"><span data-stu-id="39a3d-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="39a3d-109">Явно укажите элемент с `Me` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="39a3d-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a3d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="39a3d-110">See also</span></span>
- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="39a3d-111">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="39a3d-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
