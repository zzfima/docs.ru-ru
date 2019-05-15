---
title: Устранение рисков. Службы WCF и проверка подлинности сертификатов
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f94cabb482a237395854fcdc91df476c567069c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599511"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="abc10-102">Устранение рисков. Службы WCF и проверка подлинности сертификатов</span><span class="sxs-lookup"><span data-stu-id="abc10-102">Mitigation: WCF Services and Certificate Authentication</span></span>
<span data-ttu-id="abc10-103">В платформе .NET Framework 4.6 в список протоколов WCF SSL по умолчанию добавляются протоколы TLS 1.1 и TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="abc10-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="abc10-104">Если на клиентском компьютере и на сервере установлена платформа .NET Framework 4.6 или более поздняя версия, для согласования используется протокол TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="abc10-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="abc10-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="abc10-105">Impact</span></span>  
 <span data-ttu-id="abc10-106">Протокол TLS 1.2 не поддерживает проверку подлинности MD5.</span><span class="sxs-lookup"><span data-stu-id="abc10-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="abc10-107">В результате, если пользователь применяет SSL-сертификат, который использует хэш-алгоритм MD5, клиенту WCF не удается подключиться к службе WCF.</span><span class="sxs-lookup"><span data-stu-id="abc10-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="abc10-108">Дополнительные сведения см. в разделе [Устранение рисков. Службы WCF и проверка подлинности сертификатов](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="abc10-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="abc10-109">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="abc10-109">Mitigation</span></span>  
 <span data-ttu-id="abc10-110">Эту проблему можно решить, чтобы клиент WCF мог подключиться к серверу WCF, выполнив любое из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="abc10-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>  
  
- <span data-ttu-id="abc10-111">Обновите сертификат, чтобы он не использовал алгоритм MD5.</span><span class="sxs-lookup"><span data-stu-id="abc10-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="abc10-112">Это рекомендуемое решение.</span><span class="sxs-lookup"><span data-stu-id="abc10-112">This is the recommended solution.</span></span>  
  
- <span data-ttu-id="abc10-113">Если привязка не настроена динамически в исходном коде, обновите файл конфигурации приложения, чтобы использовать TLS 1.1 или более раннюю версию протокола.</span><span class="sxs-lookup"><span data-stu-id="abc10-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="abc10-114">Это позволяет продолжать использовать сертификат с хэш-алгоритмом MD5.</span><span class="sxs-lookup"><span data-stu-id="abc10-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="abc10-115">Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</span><span class="sxs-lookup"><span data-stu-id="abc10-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
     <span data-ttu-id="abc10-116">Это выполняется в следующем файле конфигурации:</span><span class="sxs-lookup"><span data-stu-id="abc10-116">The following configuration file does this:</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
- <span data-ttu-id="abc10-117">Если привязка настроена в исходном коде динамически, настройте свойство <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> на использование TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) или более ранней версии протокола в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="abc10-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="abc10-118">Это решение не рекомендуется, поскольку сертификат с хэш-алгоритмом MD5 считается небезопасным.</span><span class="sxs-lookup"><span data-stu-id="abc10-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abc10-119">См. также</span><span class="sxs-lookup"><span data-stu-id="abc10-119">See also</span></span>

- [<span data-ttu-id="abc10-120">Изменения среды выполнения</span><span class="sxs-lookup"><span data-stu-id="abc10-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
