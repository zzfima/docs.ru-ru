---
title: Надстройки Firefox для поддержки развертывания приложений .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 56f5f633092d8aa0bfabdb0570ec26f14221838d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124615"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Надстройки Firefox для поддержки развертывания приложений .NET
Подключаемый модуль Windows Presentation Foundation (WPF) для Firefox и помощник по .NET Framework для Firefox позволяют приложениям браузера XAML (XBAP), свободным [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]и приложениям ClickOnce работать с браузером Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Подключаемый модуль WPF для Firefox  
 Подключаемый модуль WPF для Firefox позволяет переходить между XBAP и свободными [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлами и запускать их на верхнем уровне или в элементе IFRAME HTML в браузере Firefox. XBAP — это приложение WPF, которое может быть опубликовано на веб-сервере и запущено в поддерживаемых браузерах. Свободная [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] — это файл, предназначенный только для XAML, который можно перемещать и отображать в поддерживаемых браузерах во многом подобно XML-файлу.  
  
 Подключаемый модуль WPF для Firefox устанавливается с .NET Framework 3,5. В Windows 7 имеется .NET Framework 3,5, но не входит подключаемый модуль WPF для Firefox. Невозможно установить подключаемый модуль WPF для Firefox в Windows 7.  
  
 .NET Framework 4 не включает подключаемый модуль WPF для Firefox. Однако если установлены как .NET Framework 3,5, так и .NET Framework 4, то подключаемый модуль WPF для Firefox устанавливается вместе с .NET Framework 3,5. Поэтому .NET Framework 4 приложения по-прежнему будут выполняться, так как узел WPF будет загружать правильную версию платформы. Дополнительные сведения см. в разделе [WPF Host (PresentationHost. exe)](wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>.NET Framework Assistant для Firefox  
 Помощник .NET Framework для Firefox позволяет запускать автономные приложения ClickOnce из браузера Firefox. Помощник .NET Framework для функций Firefox идентичен, когда он устанавливается до и после браузера Firefox. При запуске браузера Firefox и установке .NET Framework 3,5 с пакетом обновления 1 (SP1) Firefox находит и устанавливает помощник .NET Framework для Firefox. Пользователи могут настроить помощник .NET Framework для Firefox, чтобы сделать следующее:  
  
- Запрашивать перед запуском приложения ClickOnce.  
  
- Сообщать обо всех установленных версиях .NET Framework или только о последней версии.  
  
 Помощник .NET Framework для Firefox входит в состав .NET Framework 3,5 с пакетом обновления 1 (SP1). Сведения об удалении помощника .NET Framework для Firefox см. [в статье Удаление помощника по .NET Framework для Firefox](https://support.microsoft.com/help/963707/how-to-remove-the-net-framework-assistant-for-firefox).  
  
## <a name="see-also"></a>См. также раздел

- [Развертывание приложений WPF](deploying-a-wpf-application-wpf.md)
- [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md)
- [Проверка наличия установленного подключаемого модуля WPF для Firefox](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
