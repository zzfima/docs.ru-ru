---
title: Имена сборок и библиотек DLL
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6cf175472d68e99598dd56e170bee3d37ae3c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570436"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="1b6e4-102">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="1b6e4-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="1b6e4-103">Сборка является единицей развертывания и удостоверение для управляемого кода программы.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="1b6e4-104">Несмотря на то, что сборки могут охватывать один или несколько файлов, обычно сборки однозначное сопоставление с библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="1b6e4-105">Таким образом в этом разделе описаны только DLL соглашения об именовании, которые затем можно сопоставить соглашения об именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="1b6e4-106">**✓ СДЕЛАТЬ** выбирать имена DLL-библиотек, указывающие на больших объемов функциональные возможности, например System.Data сборки.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="1b6e4-107">Имена сборки и библиотеки DLL не обязательно должны соответствовать именам пространств имен, но следует за именем пространства имен при именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="1b6e4-108">Хорошее проверенное правило является имя библиотеки DLL, в зависимости от общего префикса пространства имен, содержащиеся в сборке.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="1b6e4-109">Например, сборки с двумя пространствами имен `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, можно вызвать `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="1b6e4-110">**✓ Попробуйте** об именовании библиотек DLL по следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="1b6e4-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="1b6e4-111">где `<Component>` содержит одно или несколько предложений, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="1b6e4-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="1b6e4-112">For example:</span></span>  
  
 <span data-ttu-id="1b6e4-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="1b6e4-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="1b6e4-114">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="1b6e4-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1b6e4-115">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="1b6e4-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6e4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1b6e4-116">See Also</span></span>  
 [<span data-ttu-id="1b6e4-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="1b6e4-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="1b6e4-118">Правила именования</span><span class="sxs-lookup"><span data-stu-id="1b6e4-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
