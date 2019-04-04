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
ms.openlocfilehash: 32aa2c1c4cd31e4591c9fa30c05ebe61058f94c5
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2019
ms.locfileid: "56442637"
---
# <a name="develop-windows-service-apps"></a>Разработка приложений службы Windows

С помощью Visual Studio или пакета SDK для .NET Framework можно легко создавать службы. Просто создайте приложение, которое устанавливается как служба. Такие приложения называются службами Windows. Используя компоненты платформы, можно создавать, устанавливать, запускать, останавливать и администрировать службы.

> [!NOTE]
> В Visual Studio можно создать службы с помощью управляемого кода на Visual C# или Visual Basic, который при необходимости может взаимодействовать с существующим кодом C++. Или можно создать службу Windows на машинном языке C++ с помощью [мастера проектов ATL](/cpp/atl/reference/atl-project-wizard).

## <a name="in-this-section"></a>Содержание раздела

[Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)

Сведения о приложениях служб Windows, времени существования служб и отличиях приложений служб от распространенных типов проектов.

[Пошаговое руководство: Создание приложения служб Windows в конструкторе компонентов](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)

Пример создания службы на Visual Basic и Visual C#.

[Программная архитектура приложений служб](../../../docs/framework/windows-services/service-application-programming-architecture.md)

Описание элементов языка, используемых при создании служб.

[Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)

Создание и настройка служб Windows с помощью шаблона проекта службы Windows.

## <a name="related-sections"></a>Связанные разделы

<xref:System.ServiceProcess.ServiceBase> — описываются основные характеристики класса <xref:System.ServiceProcess.ServiceBase>, который используется для создания служб.

<xref:System.ServiceProcess.ServiceProcessInstaller> — описываются возможности класса <xref:System.ServiceProcess.ServiceProcessInstaller>, который используется вместе с классом <xref:System.ServiceProcess.ServiceInstaller> для установки и удаления службы.

<xref:System.ServiceProcess.ServiceInstaller> — описываются возможности класса <xref:System.ServiceProcess.ServiceInstaller>, который используется вместе с классом <xref:System.ServiceProcess.ServiceProcessInstaller> для установки и удаления службы.

[Create Projects from Templates](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0fyc0azh(v=vs.120)) (Создание проектов на основе шаблонов) — описываются типы проектов, которые используются в этом разделе, и способ их выбора.
