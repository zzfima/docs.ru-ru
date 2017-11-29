---
title: "Правила именования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40da7449c88eaaba92e34374c002c7e175b2ef16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="naming-guidelines"></a><span data-ttu-id="5bc8a-102">Правила именования</span><span class="sxs-lookup"><span data-stu-id="5bc8a-102">Naming Guidelines</span></span>
<span data-ttu-id="5bc8a-103">Следующие соглашения об именовании в разработке платформы согласованного набора может быть основных вклад в удобство использования платформы.</span><span class="sxs-lookup"><span data-stu-id="5bc8a-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="5bc8a-104">Он позволяет использовать многие разработчики широко отдельных проектов платформе.</span><span class="sxs-lookup"><span data-stu-id="5bc8a-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="5bc8a-105">Помимо согласованности формы имена элементов платформы должны быть понятными и необходимо передать функции каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="5bc8a-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="5bc8a-106">В этой главе предназначена для предоставления согласованного набора соглашения об именовании, полученный в именах интерпретации смысла для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="5bc8a-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="5bc8a-107">Несмотря на то, что внедрение эти соглашения об именовании, как рекомендации по разработке обычного кода приведет к появлению более согласованное именование во всем коде, необходима только для применения их к API, которые происходят в открытую (открытые или защищенные типы и члены, и явно реализованные интерфейсы).</span><span class="sxs-lookup"><span data-stu-id="5bc8a-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bc8a-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="5bc8a-108">In This Section</span></span>  
 [<span data-ttu-id="5bc8a-109">Соглашения о регистре</span><span class="sxs-lookup"><span data-stu-id="5bc8a-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="5bc8a-110">Общие соглашения об именовании</span><span class="sxs-lookup"><span data-stu-id="5bc8a-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="5bc8a-111">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="5bc8a-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="5bc8a-112">Имена пространств имен</span><span class="sxs-lookup"><span data-stu-id="5bc8a-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="5bc8a-113">Имена классов, структур и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="5bc8a-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="5bc8a-114">Имена членов типа</span><span class="sxs-lookup"><span data-stu-id="5bc8a-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="5bc8a-115">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="5bc8a-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="5bc8a-116">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="5bc8a-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="5bc8a-117">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="5bc8a-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5bc8a-118">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="5bc8a-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc8a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5bc8a-119">See Also</span></span>  
 [<span data-ttu-id="5bc8a-120">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="5bc8a-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
