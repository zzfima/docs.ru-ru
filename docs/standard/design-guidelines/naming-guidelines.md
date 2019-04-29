---
title: Правила именования
ms.date: 10/22/2008
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
author: KrzysztofCwalina
ms.openlocfilehash: 4c7f411bdf538762de18873007c839f66911f96a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757265"
---
# <a name="naming-guidelines"></a><span data-ttu-id="9487e-102">Правила именования</span><span class="sxs-lookup"><span data-stu-id="9487e-102">Naming Guidelines</span></span>
<span data-ttu-id="9487e-103">Следуя согласованный набор соглашения об именовании при разработке инфраструктуры может быть основной свой вклад в удобство использования платформы.</span><span class="sxs-lookup"><span data-stu-id="9487e-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="9487e-104">Он позволяет платформе использовать многие разработчики широко отдельных проектов.</span><span class="sxs-lookup"><span data-stu-id="9487e-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="9487e-105">Помимо согласованности формы имена элементов платформы должны быть понятными и должен передать функции каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="9487e-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="9487e-106">В этой главе призван предоставить согласованный набор соглашений об именовании, создаются имена, которые имеют смысл для разработчиков немедленно.</span><span class="sxs-lookup"><span data-stu-id="9487e-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="9487e-107">Несмотря на то, что внедрение эти соглашения об именовании, как рекомендации по разработке обычного кода приведет к более согласованное именование по всему коду, требуется только для того, чтобы применить их к API, которые происходят в открытую (открытый или защищенный типы и члены, и явно реализованные интерфейсы).</span><span class="sxs-lookup"><span data-stu-id="9487e-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9487e-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9487e-108">In This Section</span></span>  
 [<span data-ttu-id="9487e-109">Соглашения о написании прописными буквами</span><span class="sxs-lookup"><span data-stu-id="9487e-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="9487e-110">Общие соглашения об именовании</span><span class="sxs-lookup"><span data-stu-id="9487e-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="9487e-111">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="9487e-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="9487e-112">Имена пространств имен</span><span class="sxs-lookup"><span data-stu-id="9487e-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="9487e-113">Имена классов, структур и интерфейсов</span><span class="sxs-lookup"><span data-stu-id="9487e-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="9487e-114">Имена членов типов</span><span class="sxs-lookup"><span data-stu-id="9487e-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="9487e-115">Именование параметров</span><span class="sxs-lookup"><span data-stu-id="9487e-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="9487e-116">Именование ресурсов</span><span class="sxs-lookup"><span data-stu-id="9487e-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="9487e-117">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="9487e-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9487e-118">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9487e-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9487e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9487e-119">See also</span></span>

- [<span data-ttu-id="9487e-120">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="9487e-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
