---
title: Имена сборок и библиотек DLL
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: f3c5997f777c937e9726b271afa0ae6d7a19b37d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744170"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="26f95-102">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="26f95-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="26f95-103">Сборка — это единица развертывания и идентификации для программ управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="26f95-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="26f95-104">Хотя сборки могут охватывать один или несколько файлов, обычно сборка сопоставляет один к одному с библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="26f95-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="26f95-105">Поэтому в этом разделе описываются только соглашения об именовании библиотек DLL, которые затем можно сопоставить с соглашениями об именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="26f95-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="26f95-106">✔️ выбрать имена для библиотек DLL сборки, которые предлагают большие фрагменты функциональности, такие как System. Data.</span><span class="sxs-lookup"><span data-stu-id="26f95-106">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="26f95-107">Имена сборок и библиотек DLL не должны соответствовать именам пространств имен, но при именовании сборок разумно следовать имени пространства имен.</span><span class="sxs-lookup"><span data-stu-id="26f95-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="26f95-108">Хорошим правилом Thumb является имя библиотеки DLL на основе общего префикса пространств имен, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="26f95-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="26f95-109">Например, сборка с двумя пространствами имен, `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, может быть вызвана `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="26f95-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="26f95-110">✔️ Рассмотрите возможность именования библиотек DLL в соответствии со следующим шаблоном:</span><span class="sxs-lookup"><span data-stu-id="26f95-110">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="26f95-111">где `<Component>` содержит одно или несколько предложений, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="26f95-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="26f95-112">Например:</span><span class="sxs-lookup"><span data-stu-id="26f95-112">For example:</span></span>

 <span data-ttu-id="26f95-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="26f95-113">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="26f95-114">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="26f95-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="26f95-115">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="26f95-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="26f95-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="26f95-116">See also</span></span>

- [<span data-ttu-id="26f95-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="26f95-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="26f95-118">Правила именования</span><span class="sxs-lookup"><span data-stu-id="26f95-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
