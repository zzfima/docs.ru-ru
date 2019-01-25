---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 2376a0ec25539b97a37b1827e3e4c148eb8d5838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610777"
---
# <a name="httptransportbindingelement"></a>HttpTransportBindingElement
HttpTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="methods"></a>Методы  
 Класс HttpTransportBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс HttpTransportBindingElement имеет следующие свойства.  
  
### <a name="allowcookies"></a>AllowCookies  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Значение, определяющее, принимает ли клиент файлы Cookie и распространяет ли он их на будущие запросы.  
  
### <a name="authenticationscheme"></a>AuthenticationScheme  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых HTTP-прослушивателем.  
  
### <a name="bypassproxyonlocal"></a>BypassProxyOnLocal  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее, игнорируются ли прокси-серверы для локальных адресов.  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее, используется ли имя узла для доступа к службе при сопоставлении по универсальному коду ресурса (URI).  
  
### <a name="keepaliveenabled"></a>KeepAliveEnabled  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Когда включено, соединения HTTP остаются в активном состоянии независимо от уровня активности.  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальный размер буферного пула.  
  
### <a name="proxyaddress"></a>ProxyAddress  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Универсальный код ресурса (URI), который содержит адрес прокси-сервера, используемого для выполнения HTTP-запросов.  
  
### <a name="proxyauthenticationscheme"></a>ProxyAuthenticationScheme  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Схема проверки подлинности, используемая для проверки подлинности клиентских запросов, обрабатываемых прокси-сервером HTTP.  
  
### <a name="realm"></a>Realm  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Область проверки подлинности.  
  
### <a name="transfermode"></a>TransferMode  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее статус сообщения: помещено в буфер или поток, запрос или ответ.  
  
### <a name="unsafeconnectionntlmauthentication"></a>UnsafeConnectionNtlmAuthentication  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений.  
  
### <a name="usedefaultwebproxy"></a>UseDefaultWebProxy  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее, используются ли параметры прокси-сервера компьютера или пользователя.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
