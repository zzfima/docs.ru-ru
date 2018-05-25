---
title: Разработка служебных приложений Windows
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: af6e4bf7697b3139f6809295737fdd0d90b7f013
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="developing-windows-service-applications"></a>Разработка служебных приложений Windows
С помощью Microsoft Visual Studio или пакета SDK Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] можно легко создавать службы. Просто создайте приложение, которое устанавливается как служба. Такие приложения называются службами Windows. Используя компоненты платформы, можно создавать, устанавливать, запускать, останавливать и администрировать службы.  
  
> [!WARNING]
>  Шаблон службы Windows для C++ не включен в Visual Studio 2010. Службу Windows можно создать с помощью управляемого кода на Visual C# или Visual Basic, который при необходимости может взаимодействовать с существующим кодом C++, или можно создать службу Windows на машинном языке C++ с помощью [мастера проектов ATL](/cpp/atl/reference/atl-project-wizard).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Сведения о приложениях служб Windows, времени существования служб и отличиях приложений служб от распространенных типов проектов.  
  
 [Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Пример создания службы на Visual Basic и Visual C#.  
  
 [Программная архитектура приложений служб](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Описание элементов языка, используемых при создании служб.  
  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Создание и настройка служб Windows с помощью шаблона проекта службы Windows.  
  
## <a name="related-sections"></a>Связанные разделы  
 <xref:System.ServiceProcess.ServiceBase>  
 Описываются основные характеристики класса <xref:System.ServiceProcess.ServiceBase>, который используется для создания служб.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Описываются возможности класса <xref:System.ServiceProcess.ServiceProcessInstaller>, который используется вместе с классом <xref:System.ServiceProcess.ServiceInstaller> для установки и удаления служб.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Описываются возможности класса <xref:System.ServiceProcess.ServiceInstaller>, который используется вместе с классом <xref:System.ServiceProcess.ServiceProcessInstaller> для установки и удаления службы.  
  
 [Создание проектов с помощью шаблонов (NIB)](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Описываются типы проектов, которые используются в этом разделе, и способ их выбора.
