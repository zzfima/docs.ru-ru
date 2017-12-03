---
title: HttpTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 612f2eb04ae3449fddc8fb871683b26138d046d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="dfe3e-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dfe3e-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="dfe3e-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dfe3e-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe3e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfe3e-104">Syntax</span></span>  
  
```  
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dfe3e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dfe3e-105">Methods</span></span>  
 <span data-ttu-id="dfe3e-106">Класс HttpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dfe3e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="dfe3e-107">Properties</span></span>  
 <span data-ttu-id="dfe3e-108">Класс HttpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="dfe3e-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="dfe3e-109">AllowCookies</span></span>  
 <span data-ttu-id="dfe3e-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="dfe3e-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="dfe3e-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-112">Значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="dfe3e-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="dfe3e-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="dfe3e-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="dfe3e-114">Data type: string</span></span>  
  
 <span data-ttu-id="dfe3e-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-116">Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых HTTP-прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="dfe3e-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="dfe3e-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="dfe3e-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="dfe3e-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="dfe3e-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-120">Значение, указывающее, игнорируются ли прокси-серверы для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="dfe3e-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="dfe3e-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="dfe3e-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="dfe3e-122">Data type: string</span></span>  
  
 <span data-ttu-id="dfe3e-123">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-124">Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="dfe3e-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="dfe3e-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="dfe3e-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="dfe3e-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="dfe3e-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="dfe3e-127">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-128">Когда включено, соединения HTTP остаются в активном состоянии независимо от уровня активности.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="dfe3e-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="dfe3e-129">MaxBufferSize</span></span>  
 <span data-ttu-id="dfe3e-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="dfe3e-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="dfe3e-131">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-132">Максимальный размер буферного пула.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="dfe3e-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="dfe3e-133">ProxyAddress</span></span>  
 <span data-ttu-id="dfe3e-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="dfe3e-134">Data type: string</span></span>  
  
 <span data-ttu-id="dfe3e-135">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-136">Универсальный код ресурса (URI), который содержит адрес прокси-сервера, используемого для выполнения HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="dfe3e-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="dfe3e-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="dfe3e-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="dfe3e-138">Data type: string</span></span>  
  
 <span data-ttu-id="dfe3e-139">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-140">Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых прокси-сервером HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="dfe3e-141">Realm</span><span class="sxs-lookup"><span data-stu-id="dfe3e-141">Realm</span></span>  
 <span data-ttu-id="dfe3e-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="dfe3e-142">Data type: string</span></span>  
  
 <span data-ttu-id="dfe3e-143">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-144">Область проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="dfe3e-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="dfe3e-145">TransferMode</span></span>  
 <span data-ttu-id="dfe3e-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="dfe3e-146">Data type: string</span></span>  
  
 <span data-ttu-id="dfe3e-147">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-148">Значение, указывающее статус сообщения: помещено в буфер или поток, запрос или ответ.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="dfe3e-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="dfe3e-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="dfe3e-150">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="dfe3e-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="dfe3e-151">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-152">Значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="dfe3e-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="dfe3e-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="dfe3e-154">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="dfe3e-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="dfe3e-155">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dfe3e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dfe3e-156">Значение, указывающее, используются ли параметры прокси-сервера компьютера или пользователя.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfe3e-157">Требования</span><span class="sxs-lookup"><span data-stu-id="dfe3e-157">Requirements</span></span>  
  
|<span data-ttu-id="dfe3e-158">MOF</span><span class="sxs-lookup"><span data-stu-id="dfe3e-158">MOF</span></span>|<span data-ttu-id="dfe3e-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dfe3e-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="dfe3e-160">Namespace</span></span>|<span data-ttu-id="dfe3e-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="dfe3e-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dfe3e-162">См. также</span><span class="sxs-lookup"><span data-stu-id="dfe3e-162">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
