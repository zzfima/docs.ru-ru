---
title: "Разработка служебных приложений Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 325e43f4b1734bc6ab8753285e5069f36b0fda51
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="developing-windows-service-applications"></a>Разработка служебных приложений Windows
С помощью Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, можно легко создавать службы путем создания приложения, которое устанавливается как служба. Такие приложения называются службы Windows. Используя компоненты платформы можно создавать службы, их установки и запустить, остановить и также управлять ими.  
  
> [!WARNING]
>  Шаблон службы Windows для C++ не было включено в Visual Studio 2010. Чтобы создать службу Windows, можно создать службы в управляемом коде на Visual C# или Visual Basic, который может взаимодействовать с существующим кодом C++, если это необходимо, или можно создать службу Windows на C++ с помощью [мастер проектов ATL](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Обзор приложений служб Windows, время существования службы и отличий служебного приложения от других типов проектов.  
  
 [Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Пример создания службы в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] и Visual C#.  
  
 [Программная архитектура приложений служб](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Описание элементов языка, используемых при создании служб.  
  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Описывается процесс создания и настройки служб Windows с помощью шаблона проекта службы Windows.  
  
## <a name="related-sections"></a>Связанные разделы  
 <xref:System.ServiceProcess.ServiceBase>  
 Описывает основные характеристики <xref:System.ServiceProcess.ServiceBase> класс, который используется для создания служб.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Описание возможностей <xref:System.ServiceProcess.ServiceProcessInstaller> класс, который используется вместе с <xref:System.ServiceProcess.ServiceInstaller> класса для установки и удаления служб.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Описание возможностей <xref:System.ServiceProcess.ServiceInstaller> класс, который используется вместе с <xref:System.ServiceProcess.ServiceProcessInstaller> класса для установки и удаления службы.  
  
 [NIB Создание проектов из шаблонов](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Описывает проекты, типы, используемые в этой главе и способ их выбора.
