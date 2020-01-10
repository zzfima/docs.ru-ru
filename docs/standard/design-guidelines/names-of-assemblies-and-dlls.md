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
ms.openlocfilehash: eebccba0b923b04333f289a85330d190c31013ab
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709261"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="fe513-102">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="fe513-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="fe513-103">Сборка — это единица развертывания и идентификации для программ управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="fe513-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="fe513-104">Хотя сборки могут охватывать один или несколько файлов, обычно сборка сопоставляет один к одному с библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="fe513-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="fe513-105">Поэтому в этом разделе описываются только соглашения об именовании библиотек DLL, которые затем можно сопоставить с соглашениями об именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="fe513-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="fe513-106">**✓ DO** выбирать имена DLL-библиотек, указывающие на больших объемов функциональные возможности, например System.Data сборки.</span><span class="sxs-lookup"><span data-stu-id="fe513-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="fe513-107">Имена сборок и библиотек DLL не должны соответствовать именам пространств имен, но при именовании сборок разумно следовать имени пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fe513-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="fe513-108">Хорошим правилом Thumb является имя библиотеки DLL на основе общего префикса пространств имен, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="fe513-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="fe513-109">Например, сборка с двумя пространствами имен, `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, может быть вызвана `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="fe513-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="fe513-110">**✓ CONSIDER** об именовании библиотек DLL по следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="fe513-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="fe513-111">где `<Component>` содержит одно или несколько предложений, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="fe513-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="fe513-112">Например:</span><span class="sxs-lookup"><span data-stu-id="fe513-112">For example:</span></span>  
  
 <span data-ttu-id="fe513-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="fe513-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="fe513-114">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="fe513-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="fe513-115">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="fe513-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe513-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="fe513-116">See also</span></span>

- [<span data-ttu-id="fe513-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="fe513-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="fe513-118">Правила именования</span><span class="sxs-lookup"><span data-stu-id="fe513-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
