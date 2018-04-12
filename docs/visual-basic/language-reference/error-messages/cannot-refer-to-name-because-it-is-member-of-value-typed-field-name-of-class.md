---
title: Не может ссылаться на &#39; &lt;имя&gt;&#39; поскольку он является членом поля типизированным значением &#39;&lt; имя&gt;&#39; класс &#39;&lt; className&gt;&#39; содержит &#39; System.MarshalByRefObject &#39; как базовый класс
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="795bc-102">Не может ссылаться на &#39; &lt;имя&gt;&#39; поскольку он является членом поля типизированным значением &#39;&lt; имя&gt;&#39; класс &#39;&lt; className&gt;&#39; содержит &#39; System.MarshalByRefObject &#39; как базовый класс</span><span class="sxs-lookup"><span data-stu-id="795bc-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="795bc-103">`System.MarshalByRefObject` Класс позволяет приложений, поддерживающих удаленный доступ к объектам через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="795bc-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="795bc-104">Типы должны наследовать `MarshalByRejectObject` класса при использовании типа через границы домена приложения.</span><span class="sxs-lookup"><span data-stu-id="795bc-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="795bc-105">Состояние объекта не должны копироваться, так как члены объекта не может использоваться за пределами домена приложения, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="795bc-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="795bc-106">**Идентификатор ошибки:** BC30310</span><span class="sxs-lookup"><span data-stu-id="795bc-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="795bc-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="795bc-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="795bc-108">Проверьте ссылку, чтобы убедиться в том, что член является допустимым.</span><span class="sxs-lookup"><span data-stu-id="795bc-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="795bc-109">Явно укажите элемент с `Me` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="795bc-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="795bc-110">См. также</span><span class="sxs-lookup"><span data-stu-id="795bc-110">See Also</span></span>  
 <xref:System.MarshalByRefObject>  
 [<span data-ttu-id="795bc-111">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="795bc-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
