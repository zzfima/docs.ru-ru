---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 5e23342d57621554aaec67c5c568bb75202a9454
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073745"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="df867-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="df867-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="df867-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="df867-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df867-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df867-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="df867-105">Методы</span><span class="sxs-lookup"><span data-stu-id="df867-105">Methods</span></span>  
 <span data-ttu-id="df867-106">Класс HttpTransportBindingElement не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="df867-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="df867-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="df867-107">Properties</span></span>  
 <span data-ttu-id="df867-108">Класс HttpTransportBindingElement имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="df867-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="df867-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="df867-109">AllowCookies</span></span>  
 <span data-ttu-id="df867-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="df867-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="df867-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-112">Значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.</span><span class="sxs-lookup"><span data-stu-id="df867-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="df867-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="df867-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="df867-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="df867-114">Data type: string</span></span>  
  
 <span data-ttu-id="df867-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-116">Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых HTTP-прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="df867-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="df867-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="df867-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="df867-118">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="df867-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="df867-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-120">Значение, указывающее, игнорируются ли прокси-серверы для локальных адресов.</span><span class="sxs-lookup"><span data-stu-id="df867-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="df867-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="df867-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="df867-122">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="df867-122">Data type: string</span></span>  
  
 <span data-ttu-id="df867-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-124">Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="df867-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="df867-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="df867-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="df867-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="df867-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="df867-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-128">Когда включено, соединения HTTP остаются в активном состоянии независимо от уровня активности.</span><span class="sxs-lookup"><span data-stu-id="df867-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="df867-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="df867-129">MaxBufferSize</span></span>  
 <span data-ttu-id="df867-130">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="df867-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="df867-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-132">Максимальный размер буферного пула.</span><span class="sxs-lookup"><span data-stu-id="df867-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="df867-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="df867-133">ProxyAddress</span></span>  
 <span data-ttu-id="df867-134">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="df867-134">Data type: string</span></span>  
  
 <span data-ttu-id="df867-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-136">Универсальный код ресурса (URI), который содержит адрес прокси-сервера, используемого для выполнения HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="df867-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="df867-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="df867-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="df867-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="df867-138">Data type: string</span></span>  
  
 <span data-ttu-id="df867-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-140">Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых прокси-сервером HTTP.</span><span class="sxs-lookup"><span data-stu-id="df867-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="df867-141">Realm</span><span class="sxs-lookup"><span data-stu-id="df867-141">Realm</span></span>  
 <span data-ttu-id="df867-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="df867-142">Data type: string</span></span>  
  
 <span data-ttu-id="df867-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-144">Область проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="df867-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="df867-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="df867-145">TransferMode</span></span>  
 <span data-ttu-id="df867-146">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="df867-146">Data type: string</span></span>  
  
 <span data-ttu-id="df867-147">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-148">Значение, указывающее статус сообщения: помещено в буфер или поток, запрос или ответ.</span><span class="sxs-lookup"><span data-stu-id="df867-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="df867-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="df867-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="df867-150">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="df867-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="df867-151">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-152">Значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений.</span><span class="sxs-lookup"><span data-stu-id="df867-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="df867-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="df867-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="df867-154">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="df867-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="df867-155">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="df867-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="df867-156">Значение, указывающее, используются ли параметры прокси-сервера компьютера или пользователя.</span><span class="sxs-lookup"><span data-stu-id="df867-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df867-157">Требования</span><span class="sxs-lookup"><span data-stu-id="df867-157">Requirements</span></span>  
  
|<span data-ttu-id="df867-158">MOF</span><span class="sxs-lookup"><span data-stu-id="df867-158">MOF</span></span>|<span data-ttu-id="df867-159">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="df867-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="df867-160">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="df867-160">Namespace</span></span>|<span data-ttu-id="df867-161">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="df867-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df867-162">См. также</span><span class="sxs-lookup"><span data-stu-id="df867-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
