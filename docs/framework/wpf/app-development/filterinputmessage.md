---
title: FilterInputMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e76f9863b68d5c7c34bca8adc872210527d6c17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="filterinputmessage"></a><span data-ttu-id="8f9e8-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="8f9e8-102">FilterInputMessage</span></span>
<span data-ttu-id="8f9e8-103">Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f9e8-104">Syntax</span></span>  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f9e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f9e8-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="8f9e8-106">[in] Сообщение WM_INPUT отправлено в окно, которое получает необработанные входные данные.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8f9e8-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8f9e8-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="8f9e8-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="8f9e8-108">HRESULT:</span></span>  
  
 <span data-ttu-id="8f9e8-109">S_OK — фильтр не обработал сообщение, и дальнейшая обработка разрешена.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="8f9e8-110">S_FALSE — фильтр обработал это сообщение, и дальнейшая обработка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="8f9e8-111">Значение E_NOTIMPL – Если это значение возвращается, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) не будет вызвана снова.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="8f9e8-112">Это значение может быть возвращено из ведущего приложения, которое заинтересовано только в предоставлении пользовательских интерфейсов хода выполнения и ошибок в PresentationHost.exe и не заинтересовано в перенаправлении необработанных входных сообщений из PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f9e8-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f9e8-113">Remarks</span></span>  
 <span data-ttu-id="8f9e8-114">PresentationHost.exe является целевым объектом различных необработанных устройств ввода, включая клавиатуру, мышь и удаленное управление.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="8f9e8-115">В некоторых случаях поведение в ведущем приложении зависит от входных данных, которые в противном случае будет использоваться PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="8f9e8-116">Например, ведущее приложение может зависеть от получения определенных входных сообщений, чтобы определить необходимость отображения конкретных элементов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8f9e8-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="8f9e8-117">Чтобы разрешить ведущему приложению получать необходимые входные сообщения для предоставления этих поведений, PresentationHost.exe пересылает соответствующие необработанные входные сообщения для размещенного приложения путем вызова [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span><span class="sxs-lookup"><span data-stu-id="8f9e8-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="8f9e8-118">Размещенное приложение получает необработанные входящие сообщения можно зарегистрировать в наборе устройства необработанного ввода (HID-устройства) возвращенные [Получение необработанных устройств ввода](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span><span class="sxs-lookup"><span data-stu-id="8f9e8-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9e8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8f9e8-119">See Also</span></span>  
 [<span data-ttu-id="8f9e8-120">WM_INPUT уведомления</span><span class="sxs-lookup"><span data-stu-id="8f9e8-120">WM_INPUT Notification</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
