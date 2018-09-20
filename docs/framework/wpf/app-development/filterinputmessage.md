---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1a22071696ca012968e042e15cd8a9f4b876fd9f
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46473083"
---
# <a name="filterinputmessage"></a><span data-ttu-id="c3934-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="c3934-102">FilterInputMessage</span></span>
<span data-ttu-id="c3934-103">Вызывается программой PresentationHost.exe всякий раз при получении сообщения, пока не будет возвращено E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c3934-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3934-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3934-104">Syntax</span></span>  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3934-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3934-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="c3934-106">[in] Сообщение WM_INPUT отправлено в окно, которое получает необработанные входные данные.</span><span class="sxs-lookup"><span data-stu-id="c3934-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c3934-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c3934-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="c3934-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="c3934-108">HRESULT:</span></span>  
  
 <span data-ttu-id="c3934-109">S_OK — фильтр не обработал сообщение, и дальнейшая обработка разрешена.</span><span class="sxs-lookup"><span data-stu-id="c3934-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="c3934-110">S_FALSE — фильтр обработал это сообщение, и дальнейшая обработка не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c3934-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="c3934-111">E_NOTIMPL — Если это значение возвращается, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) не вызывается повторно.</span><span class="sxs-lookup"><span data-stu-id="c3934-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="c3934-112">Это значение может быть возвращено из ведущего приложения, которое заинтересовано только в предоставлении пользовательских интерфейсов хода выполнения и ошибок в PresentationHost.exe и не заинтересовано в перенаправлении необработанных входных сообщений из PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="c3934-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3934-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3934-113">Remarks</span></span>  
 <span data-ttu-id="c3934-114">PresentationHost.exe является целевым объектом различных необработанных устройств ввода, включая клавиатуру, мышь и удаленное управление.</span><span class="sxs-lookup"><span data-stu-id="c3934-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="c3934-115">В некоторых случаях поведение в ведущем приложении зависит от входных данных, которые в противном случае будет использоваться PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="c3934-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="c3934-116">Например, ведущее приложение может зависеть от получения определенных входных сообщений, чтобы определить необходимость отображения конкретных элементов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c3934-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="c3934-117">Чтобы разрешить ведущему приложению получать необходимые входные сообщения для предоставления этих расширений функциональности, PresentationHost.exe перенаправляет соответствующие необработанные входные сообщения в размещенное приложение путем вызова [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span><span class="sxs-lookup"><span data-stu-id="c3934-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="c3934-118">Размещенное приложение получает необработанные входные сообщения путем регистрации в наборе необработанных устройств ввода (HID-устройств) возвращенные [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span><span class="sxs-lookup"><span data-stu-id="c3934-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3934-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c3934-119">See Also</span></span>  
 [<span data-ttu-id="c3934-120">Уведомление WM_INPUT</span><span class="sxs-lookup"><span data-stu-id="c3934-120">WM_INPUT Notification</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
