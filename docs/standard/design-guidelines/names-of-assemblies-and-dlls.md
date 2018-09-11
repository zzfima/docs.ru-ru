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
ms.openlocfilehash: 97bd152cff53fb1c2edb107b6d6b34bd91ca1c49
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276319"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="6d4af-102">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="6d4af-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="6d4af-103">Сборка является единицей развертывания и удостоверение для управляемого кода программы.</span><span class="sxs-lookup"><span data-stu-id="6d4af-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="6d4af-104">Несмотря на то, что сборки могут охватывать один или несколько файлов, обычно сборки взаимно-однозначное сопоставление с библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="6d4af-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="6d4af-105">Таким образом в этом разделе описывается только DLL соглашения об именовании, которые затем можно сопоставить с соглашения об именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="6d4af-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="6d4af-106">**✓ DO** выбирать имена DLL-библиотек, указывающие на больших объемов функциональные возможности, например System.Data сборки.</span><span class="sxs-lookup"><span data-stu-id="6d4af-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="6d4af-107">Имена сборки и библиотеки DLL не обязательно должны соответствовать имена пространств имен, но следует за именем пространства имен, при именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="6d4af-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="6d4af-108">Хорошее проверенное правило — это имя библиотеки DLL, в соответствии с общим префиксом пространства имен, содержащиеся в сборке.</span><span class="sxs-lookup"><span data-stu-id="6d4af-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="6d4af-109">Например, сборки с двумя пространствами имен `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, можно вызвать `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="6d4af-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="6d4af-110">**✓ CONSIDER** об именовании библиотек DLL по следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="6d4af-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="6d4af-111">где `<Component>` содержит один или несколько предложений, разделенные точками.</span><span class="sxs-lookup"><span data-stu-id="6d4af-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="6d4af-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="6d4af-112">For example:</span></span>  
  
 <span data-ttu-id="6d4af-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="6d4af-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="6d4af-114">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="6d4af-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6d4af-115">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="6d4af-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d4af-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6d4af-116">See also</span></span>

- [<span data-ttu-id="6d4af-117">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="6d4af-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="6d4af-118">Правила именования</span><span class="sxs-lookup"><span data-stu-id="6d4af-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
