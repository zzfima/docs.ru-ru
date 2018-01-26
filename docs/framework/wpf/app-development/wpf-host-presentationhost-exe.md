---
title: "Ведущее приложение WPF (PresentationHost.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c5a9df438353701932a3e732d6df28b08402ee8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-host-presentationhostexe"></a>Ведущее приложение WPF (PresentationHost.exe)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Ведущее приложение (PresentationHost.exe) — это приложение, которое позволяет размещать приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в совместимых браузерах (включая [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] и более поздние версии). По умолчанию ведущее приложение [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] регистрируется в качестве оболочки и обработчика [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] для размещенного в браузере [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] содержимого, которое включает:  
  
-   Свободные (нескомпилированные) файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (.xaml).  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap).  
  
 Для файлов этих типов ведущее приложение [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]:  
  
-   Запускает зарегистрированный обработчик [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] для размещения содержимого [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
-   Загружает правильные версии требуемых сборок [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] и [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
-   Обеспечивает наличие соответствующих уровней разрешений для зоны развертывания.  
  
 В этом разделе описываются параметры командной строки, которые можно использовать с PresentationHost.exe.  
  
## <a name="usage"></a>Использование  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|filename|Путь к файлу, который нужно активировать. Также может быть [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].|  
|-debug|При активации приложения не фиксирует его в хранилище и не запускает из хранилища. Работает только при активации локального файла.|  
|-debugSecurityZoneURL \<url>|Используется со значением [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для указания необходимости отладки PresentationHost.exe, как при развертывании из указанного [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]. Это определяет как зону развертывания, так и исходный узел.|  
|-embedding|Требуется для OLE. Если указан параметр `-event` или `-debug`, то не обязательно указывать параметр `-embedding`, поскольку он устанавливается внутренне.|  
|-event \<eventname>|Открывает событие с указанным именем и сигнализирует ему при инициализации PresentationHost.exe и готовности к размещению содержимого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Работа PresentationHost.exe будет прервана в случае ошибки при открытии события, например, если оно еще не создано.|  
|-launchApplication \<url>|Запускает автономное приложение [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] с указанного URL-адреса. Применяется политика безопасности [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] и WinINet для приложений .NET.|  
  
## <a name="scenarios"></a>Сценарии  
  
### <a name="shell-handler"></a>Обработчик оболочки  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>Обработчик MIME  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Отладка в Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>Visual Studio, отладка в зоне  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>См. также  
 [Безопасность](../../../../docs/framework/wpf/security-wpf.md)
