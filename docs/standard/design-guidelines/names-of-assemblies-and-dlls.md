---
title: "Имена сборок и библиотек DLL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 071ca1547898b80440e86df0e4cb9c0667e462ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="7b7aa-102">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="7b7aa-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="7b7aa-103">Сборка является единицей развертывания и удостоверение для управляемого кода программы.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="7b7aa-104">Несмотря на то, что сборки могут охватывать один или несколько файлов, обычно сборки однозначное сопоставление с библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="7b7aa-105">Таким образом в этом разделе описаны только DLL соглашения об именовании, которые затем можно сопоставить соглашения об именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="7b7aa-106">**✓ СДЕЛАТЬ** выбирать имена DLL-библиотек, указывающие на больших объемов функциональные возможности, например System.Data сборки.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="7b7aa-107">Имена сборки и библиотеки DLL не обязательно должны соответствовать именам пространств имен, но следует за именем пространства имен при именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="7b7aa-108">Хорошее проверенное правило является имя библиотеки DLL, в зависимости от общего префикса сборок, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-108">A good rule of thumb is to name the DLL based on the common prefix of the assemblies contained in the assembly.</span></span> <span data-ttu-id="7b7aa-109">Например, сборки с двумя пространствами имен `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, можно вызвать `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="7b7aa-110">**✓ Попробуйте** об именовании библиотек DLL по следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="7b7aa-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="7b7aa-111">где `<Component>` содержит одно или несколько предложений, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="7b7aa-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="7b7aa-112">For example:</span></span>  
  
 <span data-ttu-id="7b7aa-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="7b7aa-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="7b7aa-114">*Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="7b7aa-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="7b7aa-115">*Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="7b7aa-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b7aa-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7b7aa-116">See Also</span></span>  
 [<span data-ttu-id="7b7aa-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="7b7aa-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="7b7aa-118">Правила именования</span><span class="sxs-lookup"><span data-stu-id="7b7aa-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
