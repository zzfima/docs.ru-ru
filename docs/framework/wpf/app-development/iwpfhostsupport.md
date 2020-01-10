---
title: Интерфейс IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 4855fae2954e5650d8c9bbb81153ebe64249a867
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740195"
---
# <a name="iwpfhostsupport"></a>Интерфейс IWpfHostSupport
Приложения, которые размещают [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] содержимое через PresentationHost. exe, реализуют этот интерфейс для обеспечения точки интеграции между узлом и PresentationHost. exe.  
  
## <a name="remarks"></a>Заметки  
 Приложения Win32, такие как веб-браузеры, могут размещать содержимое WPF, включая приложения браузера XAML (XBAP) и свободный XAML. Для размещения содержимого WPF приложения Win32 создают экземпляр [элемента управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911). Для размещения WPF создает экземпляр PresentationHost. exe, который обеспечивает размещение содержимого WPF на узле для показа в [элементе управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 Интеграция, включенная `IWpfHostSupport`, позволяет PresentationHost. exe:  
  
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
