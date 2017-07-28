---
title: "Ведущее приложение WPF (PresentationHost.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PresentationHost.exe"
  - "WPF - ведущее приложение"
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Ведущее приложение WPF (PresentationHost.exe)
Приложение [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host \(PresentationHost.exe\) позволяет размещать приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в совместимых браузерах \(включая [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] и более поздние версии\).  По умолчанию [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host зарегистрирован в качестве оболочки и обработчика [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] для браузерного [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] содержимого, которое включает:  
  
-   Свободные \(нескомпилированные\) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлы \(.xaml\).  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] \(.xbap\).  
  
 Для файлов этих типов, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:  
  
-   Запускает зарегистрированный [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] обработчик для размещения [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] содержимого.  
  
-   Загружает верные версии требуемых [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] и [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] сборок.  
  
-   Обеспечивает установку соответствующих уровней разрешений для зоны развертывания.  
  
 В этом разделе описываются параметры командной строки, которые могут быть использованы с PresentationHost.exe.  
  
## Использование  
 `PresentationHost.exe [parameters] uri|filename`  
  
## Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|filename|Путь к активируемому файлу.  Также может быть [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].|  
|\-отладка|При активации приложения не фиксировать или не запускать его из хранилища.  Это работает только тогда, когда активируется локальный файл.|  
|\-debugSecurityZoneURL \<url\>|Используется со значением [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] для обозначения PresentationHost.exe, что приложение должно быть отлажено, как если бы оно было развернуто из указанного [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].  Это определяет зону развертывания и начальный веб\-узел.|  
|\-embedding|Требуется при OLE.  Если указан параметр `-event` или `-debug`, то указывать параметр `-embedding` необязательно, поскольку он устанавливается внутри.|  
|\-событие \<имя\_события\>|Откройте событие с указанным именем и укажите его при инициализации и готовности PresentationHost.exe разместить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] содержимое.  PresentationHost.exe будет завершен, если произошла ошибка при открытии события, например, если оно еще не было создано.|  
|\-launchApplication \<url\>|Запускает автономное приложение [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] с указанного URL\-адреса.  Применяется политика безопасности [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] и WinINet в отношении приложений .NET.|  
  
## Сценарии  
  
### Обработчик оболочки  
 `PresentationHost.exe example.xbap`  
  
### обработчик MIME  
 `PresentationHost.exe -embedding example.xbap`  
  
### Отладка Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### Отладка Visual Studio в Зоне  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## См. также  
 [Безопасность](../../../../docs/framework/wpf/security-wpf.md)