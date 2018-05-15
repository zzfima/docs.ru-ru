---
title: Правила именования
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53ffb641d3e507a937c304725b3c8590d046338e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="naming-guidelines"></a><span data-ttu-id="30f89-102">Правила именования</span><span class="sxs-lookup"><span data-stu-id="30f89-102">Naming Guidelines</span></span>
<span data-ttu-id="30f89-103">Следующие соглашения об именовании в разработке платформы согласованного набора может быть основных вклад в удобство использования платформы.</span><span class="sxs-lookup"><span data-stu-id="30f89-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="30f89-104">Он позволяет использовать многие разработчики широко отдельных проектов платформе.</span><span class="sxs-lookup"><span data-stu-id="30f89-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="30f89-105">Помимо согласованности формы имена элементов платформы должны быть понятными и необходимо передать функции каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="30f89-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="30f89-106">В этой главе предназначена для предоставления согласованного набора соглашения об именовании, полученный в именах интерпретации смысла для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="30f89-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="30f89-107">Несмотря на то, что внедрение эти соглашения об именовании, как рекомендации по разработке обычного кода приведет к появлению более согласованное именование во всем коде, необходима только для применения их к API, которые происходят в открытую (открытые или защищенные типы и члены, и явно реализованные интерфейсы).</span><span class="sxs-lookup"><span data-stu-id="30f89-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30f89-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="30f89-108">In This Section</span></span>  
 [<span data-ttu-id="30f89-109">Соглашения о написании прописными буквами</span><span class="sxs-lookup"><span data-stu-id="30f89-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="30f89-110">Общие соглашения об именовании</span><span class="sxs-lookup"><span data-stu-id="30f89-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="30f89-111">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="30f89-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="30f89-112">Имена пространств имен</span><span class="sxs-lookup"><span data-stu-id="30f89-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="30f89-113">Имена классов, структур и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="30f89-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="30f89-114">Имена членов типов</span><span class="sxs-lookup"><span data-stu-id="30f89-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="30f89-115">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="30f89-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="30f89-116">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="30f89-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="30f89-117">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="30f89-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="30f89-118">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="30f89-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f89-119">См. также</span><span class="sxs-lookup"><span data-stu-id="30f89-119">See Also</span></span>  
 [<span data-ttu-id="30f89-120">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="30f89-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
