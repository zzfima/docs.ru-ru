---
title: Интерфейс IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964785"
---
# <a name="iwpfhostsupport"></a>Интерфейс IWpfHostSupport
Приложения, на [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] которых размещается содержимое с помощью PresentationHost. exe, реализуют этот интерфейс для обеспечения точки интеграции между узлом и PresentationHost. exe.  
  
## <a name="remarks"></a>Примечания  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]такие приложения, как веб-браузеры, могут [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] размещать [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимое, включая и свободный код XAML. Для размещения [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] содержимого приложения создают экземпляр [элемента управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911). Для размещения [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] служб создает экземпляр PresentationHost. exe, который предоставляет размещенное [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] содержимое на узле для показа в [элементе управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 Интеграция, включенная `IWpfHostSupport` в, позволяет PresentationHost. exe:  
  
- Обнаружение и регистрация с помощью необработанных устройств ввода (устройств с HID-интерфейсом), в которых заинтересован ведущее приложение.  
  
- Получение входных сообщений с зарегистрированных устройств ввода необработанных данных и пересылка соответствующих сообщений ведущему приложению.  
  
- Запросите ведущее приложение для пользовательского пользовательского интерфейса хода выполнения и ошибок.  
  
> [!NOTE]
> Этот API предназначен и поддерживается только для использования на локальном клиентском компьютере  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Позволяет программе PresentationHost.exe обнаруживать устройства необработанного ввода (устройства HID), которые интересуют ведущее приложение.|  
|[FilterInputMessage](filterinputmessage.md)|Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.|  
|[GetCustomUI](getcustomui.md)|По умолчанию PresentationHost. exe предоставляет собственный ход развертывания и пользовательские интерфейсы ошибок развертывания, отображаемые при развертывании содержимого WPF.|
