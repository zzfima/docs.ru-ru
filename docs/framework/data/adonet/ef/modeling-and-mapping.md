---
title: "Моделирование и сопоставление"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2004b950f1096f574734259ba02944577dd9adc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="modeling-and-mapping"></a><span data-ttu-id="b2b7b-102">Моделирование и сопоставление</span><span class="sxs-lookup"><span data-stu-id="b2b7b-102">Modeling and Mapping</span></span>
<span data-ttu-id="b2b7b-103">Платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] позволяет определить концептуальную модель, модель хранения и сопоставление между ними, которые оптимальным образом подходят для приложения.</span><span class="sxs-lookup"><span data-stu-id="b2b7b-103">In the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you can define the conceptual model, storage model, and the mapping between the two in the way that best suits your application.</span></span> <span data-ttu-id="b2b7b-104">Средства модели EDM в [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] позволяют создавать.[ EDMX-файла](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) из базы данных или графической модели и обновите его при изменении модели или базы данных.</span><span class="sxs-lookup"><span data-stu-id="b2b7b-104">The Entity Data Model Tools in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] allow you to create an .[edmx file](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4) from a database or a graphical model and then update that file when either the database or model changes.</span></span>  
  
 <span data-ttu-id="b2b7b-105">Начиная с версии 4.1 платформы Entity Framework модель можно также создавать программно с помощью шаблона разработки Code First.</span><span class="sxs-lookup"><span data-stu-id="b2b7b-105">Starting with the Entity Framework 4.1 you can also create a model programmatically using Code First development.</span></span> <span data-ttu-id="b2b7b-106">Шаблон разработки Code First имеет два различных сценария.</span><span class="sxs-lookup"><span data-stu-id="b2b7b-106">There are two different scenarios for Code First development.</span></span> <span data-ttu-id="b2b7b-107">В обоих случаях разработчик определяет модель, задавая в коде определения классов .NET Framework, а затем выборочно определяет дополнительные сопоставления или конфигурации с помощью заметок к данным или fluent API.</span><span class="sxs-lookup"><span data-stu-id="b2b7b-107">In both cases, the developer defines a model by coding .NET Framework class definitions, and then optionally specifies additional mapping or configuration by using Data Annotations or the fluent API.</span></span>  
  
 <span data-ttu-id="b2b7b-108">Дополнительные сведения см. в разделе [Создание и сопоставление концептуальной модели](http://go.microsoft.com/fwlink/?LinkId=235016).</span><span class="sxs-lookup"><span data-stu-id="b2b7b-108">For more information, see [Creating and Mapping a Conceptual Model](http://go.microsoft.com/fwlink/?LinkId=235016).</span></span>  
  
 <span data-ttu-id="b2b7b-109">Можно также использовать генератор модели EDM, который входит в состав [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2b7b-109">You can also use the EDM Generator, which is included with the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="b2b7b-110">Программа EdmGen.exe формирует файлы языка CSDL, SSDL и MSL на основе существующего источника данных.</span><span class="sxs-lookup"><span data-stu-id="b2b7b-110">The EdmGen.exe generates the .csdl, .ssdl, and .msl files from an existing data source.</span></span> <span data-ttu-id="b2b7b-111">Можно также вручную создать содержимое модели и сопоставления.</span><span class="sxs-lookup"><span data-stu-id="b2b7b-111">You can also manually create the model and mapping content.</span></span> <span data-ttu-id="b2b7b-112">Дополнительные сведения см. в разделе [генератор модели EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b2b7b-112">For more information, see [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).</span></span>
