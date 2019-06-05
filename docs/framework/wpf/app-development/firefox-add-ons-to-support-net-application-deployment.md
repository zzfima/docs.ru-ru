---
title: Надстройки Firefox для поддержки развертывания приложений .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: e018048df70470e349f06ac80e7a597cd742dac5
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690515"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Надстройки Firefox для поддержки развертывания приложений .NET
Включить Windows Presentation Foundation (WPF) подключаемого модуля для Firefox и .NET Framework Assistant для Firefox [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]и приложений ClickOnce для работы с браузером Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Подключаемого модуля WPF для Firefox  
 Включение подключаемого модуля WPF для Firefox [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] и свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлы, чтобы перейти и запустить на верхнем уровне или в IFRAME HTML в браузере Firefox. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Является [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения, опубликованные на веб-сервере и запустить в поддерживаемых браузеров. Свободные [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] является файлом только для XAML, который можно перейти и в поддерживаемых браузерах, как XML-файл.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Подключаемый модуль для Firefox устанавливается вместе с .NET Framework 3.5. Windows 7 включает в себя .NET Framework 3.5, но не включает [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] подключаемого модуля для Firefox. Не удается установить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] подключаемого модуля для Firefox в Windows 7.  
  
 .NET Framework 4 не включает [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] подключаемого модуля для Firefox. Тем не менее если установлены .NET Framework 4 и .NET Framework 3.5, подключаемого модуля WPF для Firefox устанавливается с .NET Framework 3.5. Таким образом приложений .NET Framework 4 будет работать, поскольку ведущее приложение WPF загрузит правильную версию платформы. Дополнительные сведения см. в разделе [ведущее приложение WPF (PresentationHost.exe)](wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant для Firefox  
 .NET Framework Assistant для Firefox позволяет выполнять из браузера Firefox автономного приложения ClickOnce. .NET Framework Assistant для Firefox функций идентично в том случае, если он установлен до и после браузер Firefox. При запуске браузера Firefox и [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] будет установлено, Firefox находит и устанавливает .NET Framework Assistant для Firefox. Пользователи могут настраивать .NET Framework Assistant для Firefox, выполнив следующие действия:  
  
- Запрашивать перед запуском приложения ClickOnce.  
  
- Сообщать о всех установленных версий .NET Framework или только о последней версии.  
  
 .NET Framework Assistant для Firefox входит в состав [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Сведения об удалении .NET Framework Assistant для Firefox, см. в разделе [удаление .NET Framework Assistant для Firefox](https://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>См. также

- [Развертывание приложений WPF](deploying-a-wpf-application-wpf.md)
- [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md)
- [Проверка наличия установленного подключаемого модуля WPF для Firefox](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
