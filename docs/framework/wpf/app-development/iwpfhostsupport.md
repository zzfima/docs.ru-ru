---
title: Интерфейс IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 51964358d27a16d9840e29be06c11f57de2fad23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iwpfhostsupport"></a>Интерфейс IWpfHostSupport
Приложения, размещающие [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимым при помощи PresentationHost.exe реализуют этот интерфейс для предоставления точки интеграции между узлом и PresentationHost.exe.  
  
## <a name="remarks"></a>Примечания  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] можно размещать приложения, такие как веб-браузеры [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимого, включая [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и Свободный XAML. Узел [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимое, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] приложения создают экземпляр [элемент управления WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911). Для размещения [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] создает экземпляр PresentationHost.exe, который предоставляет размещаемый [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимого на узел для отображения в [элемент управления WebBrowser](http://go.microsoft.com/fwlink/?LinkId=97911).  
  
 Интеграция включаемые `IWpfHostSupport` позволяет PresentationHost.exe для:  
  
-   Определить и зарегистрировать устройства необработанного ввода (HID-устройства), которых интересует ведущего приложения.  
  
-   Получение входных сообщений от зарегистрированного устройства необработанного ввода и переслать соответствующие сообщения в ведущее приложение.  
  
-   Запрос ведущего приложения для пользовательских интерфейсов пользователя хода выполнения и ошибки.  
  
> [!NOTE]
>  Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|По умолчанию PresentationHost.exe время от времени предоставляет свой собственный ход выполнения развертывания и ошибка развертывания при пользовательские интерфейсы, которые отображаются при развертывании содержимого WPF.|
