---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: bd696752a287a78533d55c0fd3ad9986a32bd180
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052213"
---
# <a name="filterinputmessage"></a>FilterInputMessage
Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
## <a name="parameters"></a>Параметры  
 `pMsg`  
  
 [in] Сообщение WM_INPUT отправлено в окно, которое получает необработанные входные данные.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT:  
  
 S_OK — фильтр не обработал сообщение, и дальнейшая обработка разрешена.  
  
 S_FALSE — фильтр обработал это сообщение, и дальнейшая обработка не выполняется.  
  
 E_NOTIMPL — Если это значение возвращается, [FilterInputMessage](filterinputmessage.md) не вызывается повторно. Это значение может быть возвращено из ведущего приложения, которое заинтересовано только в предоставлении пользовательских интерфейсов хода выполнения и ошибок в PresentationHost.exe и не заинтересовано в перенаправлении необработанных входных сообщений из PresentationHost.exe.  
  
## <a name="remarks"></a>Примечания  
 PresentationHost.exe является целевым объектом различных необработанных устройств ввода, включая клавиатуру, мышь и удаленное управление. В некоторых случаях поведение в ведущем приложении зависит от входных данных, которые в противном случае будет использоваться PresentationHost.exe. Например, ведущее приложение может зависеть от получения определенных входных сообщений, чтобы определить необходимость отображения конкретных элементов пользовательского интерфейса.  
  
 Чтобы разрешить ведущему приложению получать необходимые входные сообщения для предоставления этих расширений функциональности, PresentationHost.exe перенаправляет соответствующие необработанные входные сообщения в размещенное приложение путем вызова [FilterInputMessage](filterinputmessage.md).  
  
 Размещенное приложение получает необработанные входные сообщения путем регистрации в наборе необработанных устройств ввода (HID-устройств) возвращенные [GetRawInputDevices](getrawinputdevices.md).  
  
## <a name="see-also"></a>См. также

- [Сообщение WM_INPUT](/windows/desktop/inputdev/wm-input)
