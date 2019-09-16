---
title: Предоставление динамических методов и сборок
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 767382f27a96e8aacce4cc625de610949b3f02a3
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971040"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="c9094-102">Предоставление динамических методов и сборок</span><span class="sxs-lookup"><span data-stu-id="c9094-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="c9094-103">В этом разделе описывается набор управляемых типов в пространстве имен <xref:System.Reflection.Emit>, позволяющий компилятору или средству порождать метаданные и код MSIL во время выполнения, а также при необходимости создавать переносимый исполняемый (PE) файл на диске.</span><span class="sxs-lookup"><span data-stu-id="c9094-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="c9094-104">Основными пользователями этого пространства имен являются обработчики скриптов и компиляторы.</span><span class="sxs-lookup"><span data-stu-id="c9094-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="c9094-105">В этом разделе функциональные возможности, предоставляемые пространством имен <xref:System.Reflection.Emit>, называются порождением отражения.</span><span class="sxs-lookup"><span data-stu-id="c9094-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="c9094-106">Порождение отражения предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="c9094-106">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="c9094-107">определение облегченных глобальных методов во время выполнения с помощью класса <xref:System.Reflection.Emit.DynamicMethod> и их выполнение с помощью делегатов;</span><span class="sxs-lookup"><span data-stu-id="c9094-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="c9094-108">определение сборок во время выполнения и последующий их запуск или сохранение на диск;</span><span class="sxs-lookup"><span data-stu-id="c9094-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="c9094-109">определение сборок во время выполнения с последующим их запуском, выгрузкой и предоставлением сборке мусора разрешения на получение их ресурсов;</span><span class="sxs-lookup"><span data-stu-id="c9094-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="c9094-110">определение модулей в новых сборках во время выполнения с последующим их запуском или сохранением на диске;</span><span class="sxs-lookup"><span data-stu-id="c9094-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="c9094-111">определение типов в модулях во время выполнения, создание экземпляров этих типов и вызов их методов;</span><span class="sxs-lookup"><span data-stu-id="c9094-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="c9094-112">определение символьной информации для определяемых модулей, которая может использоваться такими средствами, как отладчики и профилировщики кода.</span><span class="sxs-lookup"><span data-stu-id="c9094-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="c9094-113">Наряду с управляемыми типами в пространстве имен <xref:System.Reflection.Emit> существуют неуправляемые интерфейсы метаданных, которые описаны в статье [Интерфейсы метаданных](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) справочной документации.</span><span class="sxs-lookup"><span data-stu-id="c9094-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="c9094-114">Управляемое порождение отражения обеспечивает более строгую проверку семантических ошибок и более высокий уровень абстрагирования метаданных, чем неуправляемые интерфейсы метаданных.</span><span class="sxs-lookup"><span data-stu-id="c9094-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="c9094-115">Другим полезным ресурсом для работы с метаданными и кодом MSIL является документация Common Language Infrastructure (CLI), особенно "Раздел II. Определение метаданных и семантика" и "Раздел III. Набор инструкций CIL".</span><span class="sxs-lookup"><span data-stu-id="c9094-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="c9094-116">Документацию можно найти на сайтах [MSDN](https://go.microsoft.com/fwlink/?LinkID=65555) и [ECMA](https://go.microsoft.com/fwlink/?LinkId=116487).</span><span class="sxs-lookup"><span data-stu-id="c9094-116">The documentation is available online on [MSDN](https://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](https://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9094-117">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c9094-117">In This Section</span></span>
  
[<span data-ttu-id="c9094-118">Вопросы безопасности в порождении отражения</span><span class="sxs-lookup"><span data-stu-id="c9094-118">Security issues in reflection emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
<span data-ttu-id="c9094-119">Описываются проблемы безопасности, связанные с созданием динамических сборок с помощью порождения отражения.</span><span class="sxs-lookup"><span data-stu-id="c9094-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="c9094-120">[Практическое руководство. Определение и выполнение динамических методов](how-to-define-and-execute-dynamic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="c9094-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) </span></span>  
<span data-ttu-id="c9094-121">Показывает способы определения и выполнения простого динамического метода и динамического метода, привязанного к экземпляру класса.</span><span class="sxs-lookup"><span data-stu-id="c9094-121">Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="c9094-122">[Практическое руководство. Определение универсального типа с помощью выпуска отражения](how-to-define-a-generic-type-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="c9094-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) </span></span>  
<span data-ttu-id="c9094-123">Описывает способы создания простого универсального типа с двумя параметрами типа, применение ограничений класса, ограничений интерфейса и специальных ограничений для параметров типа, создание элементов, использующих параметры типа класса в качестве типов параметров и типов возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="c9094-123">Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="c9094-124">[Практическое руководство. Определение универсального метода с помощью выпуска отражения](how-to-define-a-generic-method-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="c9094-124">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) </span></span>  
<span data-ttu-id="c9094-125">Показывает, как создать, породить и вызвать простой универсальный метод.</span><span class="sxs-lookup"><span data-stu-id="c9094-125">Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="c9094-126">[Забираемые сборки для динамической генерации типа](collectible-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="c9094-126">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) </span></span>  
<span data-ttu-id="c9094-127">Представляет забираемые сборки, то есть динамические сборки, которые можно выгрузить без выгрузки домена приложения, в котором они были созданы.</span><span class="sxs-lookup"><span data-stu-id="c9094-127">Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="c9094-128">Справочник</span><span class="sxs-lookup"><span data-stu-id="c9094-128">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="c9094-129">Каталог кодов инструкций MSIL, которые можно использовать для построения тел методов.</span><span class="sxs-lookup"><span data-stu-id="c9094-129">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="c9094-130">Содержит управляемые классы, используемые для порождения динамических методов, сборок и типов.</span><span class="sxs-lookup"><span data-stu-id="c9094-130">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="c9094-131">Описывается класс <xref:System.Type>, который представляет типы в управляемом отражении и порождении отражения и является ключевым элементом при использовании этих технологий.</span><span class="sxs-lookup"><span data-stu-id="c9094-131">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="c9094-132">Содержит управляемые классы, используемые для просмотра метаданных и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="c9094-132">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9094-133">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c9094-133">Related Sections</span></span>  
 [<span data-ttu-id="c9094-134">Отражение</span><span class="sxs-lookup"><span data-stu-id="c9094-134">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="c9094-135">Описываются способы просмотра метаданных и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="c9094-135">Explains how to explore metadata and managed code.</span></span>  
  
 [<span data-ttu-id="c9094-136">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="c9094-136">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
 <span data-ttu-id="c9094-137">Предоставляет обзор сборок в реализациях .NET.</span><span class="sxs-lookup"><span data-stu-id="c9094-137">Provides an overview of assemblies in .NET implementations.</span></span>
