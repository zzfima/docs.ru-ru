---
title: Ведущее приложение WPF (PresentationHost.exe)
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: bda7efbb1b7a4760199215bdb58c12b3063e290c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743397"
---
# <a name="wpf-host-presentationhostexe"></a>Ведущее приложение WPF (PresentationHost.exe)
Узел Windows Presentation Foundation (WPF) (PresentationHost. exe) — это приложение, которое позволяет размещать приложения WPF в совместимых браузерах (включая Microsoft Internet Explorer 6 и более поздние версии). По умолчанию узел Windows Presentation Foundation (WPF) регистрируется в качестве оболочки и обработчика MIME для содержимого WPF, размещенного в браузере, в том числе:  
  
- Свободные (нескомпилированные) файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (.xaml).  
  
- Приложение браузера XAML (XBAP).  
  
 Для файлов этих типов Windows Presentation Foundation (WPF):  
  
- Запускает зарегистрированный обработчик HTML для размещения содержимого Windows Presentation Foundation (WPF).  
  
- Загружает правильные версии требуемых сборок среды CLR и Windows Presentation Foundation (WPF).  
  
- Обеспечивает наличие соответствующих уровней разрешений для зоны развертывания.  
  
 В этом разделе описываются параметры командной строки, которые можно использовать с PresentationHost.exe.  
  
## <a name="usage"></a>Использование  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Description|  
|---------------|-----------------|  
|filename|Путь к файлу, который нужно активировать. Также может быть URI.|  
|-debug|При активации приложения не фиксирует его в хранилище и не запускает из хранилища. Работает только при активации локального файла.|  
|-debugSecurityZoneURL \<url>|Используется со значением URL-адреса, чтобы указать PresentationHost. exe, что приложение должно быть отлажено, как если бы оно было развернуто с указанного URL-адреса. Это определяет как зону развертывания, так и исходный узел.|  
|-embedding|Требуется для OLE. Если указан параметр `-event` или `-debug`, то не обязательно указывать параметр `-embedding`, поскольку он устанавливается внутренне.|  
|-event \<eventname>|Откройте событие с этим именем и задаст его при инициализации PresentationHost. exe и готовности к размещению содержимого WPF. Работа PresentationHost.exe будет прервана в случае ошибки при открытии события, например, если оно еще не создано.|  
|-launchApplication \<url>|Запускает автономное приложение ClickOnce по указанному URL-адресу. Применяются политики безопасности Internet Explorer и WinINet в отношении приложений .NET.|  
  
## <a name="scenarios"></a>Сценарии  
  
### <a name="shell-handler"></a>Обработчик оболочки  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>Обработчик MIME  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Отладка в Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>Visual Studio, отладка в зоне  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>См. также раздел

- [Безопасность](../security-wpf.md)
