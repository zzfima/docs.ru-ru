---
title: "Предоставление динамических методов и сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.assetid: 8e8e2631-62fd-40e7-a8ee-0039b06749bc
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c28a5b71a93ea5159adc73316771d490dbe0db87
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="69d03-102">Предоставление динамических методов и сборок</span><span class="sxs-lookup"><span data-stu-id="69d03-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="69d03-103">В этом разделе описывается набор управляемых типов в пространстве имен <xref:System.Reflection.Emit>, позволяющий компилятору или средству порождать метаданные и код MSIL во время выполнения, а также при необходимости создавать переносимый исполняемый (PE) файл на диске.</span><span class="sxs-lookup"><span data-stu-id="69d03-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="69d03-104">Основными пользователями этого пространства имен являются обработчики скриптов и компиляторы.</span><span class="sxs-lookup"><span data-stu-id="69d03-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="69d03-105">В этом разделе функциональные возможности, предоставляемые пространством имен <xref:System.Reflection.Emit>, называются порождением отражения.</span><span class="sxs-lookup"><span data-stu-id="69d03-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="69d03-106">Порождение отражения предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="69d03-106">Reflection emit provides the following capabilities:</span></span>  
  
-   <span data-ttu-id="69d03-107">определение облегченных глобальных методов во время выполнения с помощью класса <xref:System.Reflection.Emit.DynamicMethod> и их выполнение с помощью делегатов;</span><span class="sxs-lookup"><span data-stu-id="69d03-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
-   <span data-ttu-id="69d03-108">определение сборок во время выполнения и последующий их запуск или сохранение на диск;</span><span class="sxs-lookup"><span data-stu-id="69d03-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="69d03-109">определение сборок во время выполнения с последующим их запуском, выгрузкой и предоставлением сборке мусора разрешения на получение их ресурсов;</span><span class="sxs-lookup"><span data-stu-id="69d03-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
-   <span data-ttu-id="69d03-110">определение модулей в новых сборках во время выполнения с последующим их запуском или сохранением на диске;</span><span class="sxs-lookup"><span data-stu-id="69d03-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="69d03-111">определение типов в модулях во время выполнения, создание экземпляров этих типов и вызов их методов;</span><span class="sxs-lookup"><span data-stu-id="69d03-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
-   <span data-ttu-id="69d03-112">определение символьной информации для определяемых модулей, которая может использоваться такими средствами, как отладчики и профилировщики кода.</span><span class="sxs-lookup"><span data-stu-id="69d03-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="69d03-113">Наряду с управляемыми типами в пространстве имен <xref:System.Reflection.Emit> существуют неуправляемые интерфейсы метаданных, которые описаны в статье [Интерфейсы метаданных](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) справочной документации.</span><span class="sxs-lookup"><span data-stu-id="69d03-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="69d03-114">Управляемое порождение отражения обеспечивает более строгую проверку семантических ошибок и более высокий уровень абстрагирования метаданных, чем неуправляемые интерфейсы метаданных.</span><span class="sxs-lookup"><span data-stu-id="69d03-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="69d03-115">Другим полезным ресурсом для работы с метаданными и кодом MSIL является документация по инфраструктуре Common Language Infrastructure (CLI), особенно раздел II, посвященный определению и семантике метаданных, и раздел III, посвященный набору инструкций CIL.</span><span class="sxs-lookup"><span data-stu-id="69d03-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="69d03-116">Документацию можно найти на сайтах [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) и [ECMA](http://go.microsoft.com/fwlink/?LinkId=116487).</span><span class="sxs-lookup"><span data-stu-id="69d03-116">The documentation is available online on [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](http://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69d03-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="69d03-117">In This Section</span></span>  
 [<span data-ttu-id="69d03-118">Вопросы безопасности в порождении отражения</span><span class="sxs-lookup"><span data-stu-id="69d03-118">Security Issues in Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
 <span data-ttu-id="69d03-119">Описываются проблемы безопасности, связанные с созданием динамических сборок с помощью порождения отражения.</span><span class="sxs-lookup"><span data-stu-id="69d03-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="69d03-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="69d03-120">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="69d03-121">Каталог кодов инструкций MSIL, которые можно использовать для построения тел методов.</span><span class="sxs-lookup"><span data-stu-id="69d03-121">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="69d03-122">Содержит управляемые классы, используемые для порождения динамических методов, сборок и типов.</span><span class="sxs-lookup"><span data-stu-id="69d03-122">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="69d03-123">Описывается класс <xref:System.Type>, который представляет типы в управляемом отражении и порождении отражения и является ключевым элементом при использовании этих технологий.</span><span class="sxs-lookup"><span data-stu-id="69d03-123">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="69d03-124">Содержит управляемые классы, используемые для просмотра метаданных и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="69d03-124">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="69d03-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="69d03-125">Related Sections</span></span>  
 [<span data-ttu-id="69d03-126">Отражение</span><span class="sxs-lookup"><span data-stu-id="69d03-126">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="69d03-127">Описываются способы просмотра метаданных и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="69d03-127">Explains how to explore metadata and managed code.</span></span>  
  
 [<span data-ttu-id="69d03-128">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="69d03-128">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="69d03-129">Обзор сборок в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69d03-129">Provides an overview of assemblies in the .NET Framework.</span></span>

