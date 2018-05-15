---
title: Практическое руководство. Согласованное обращение к сертификатам X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: efc4fb399224de7f03c6bffb606178184de1d467
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="0c395-102">Практическое руководство. Согласованное обращение к сертификатам X.509</span><span class="sxs-lookup"><span data-stu-id="0c395-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="0c395-103">Существует несколько способов идентификации сертификата: с помощью хэша сертификата, имени поставщика и серийного номера, а также идентификатора ключа субъекта (SKI).</span><span class="sxs-lookup"><span data-stu-id="0c395-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="0c395-104">Идентификатор ключа субъекта (SKI) обеспечивает уникальную идентификацию открытого ключа субъекта сертификата, поэтому он часто используется при работе с цифровой подписью XML.</span><span class="sxs-lookup"><span data-stu-id="0c395-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="0c395-105">Данное значение обычно является частью сертификата X.509 в виде *расширения сертификатов X.509*.</span><span class="sxs-lookup"><span data-stu-id="0c395-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="0c395-106">Windows Communication Foundation (WCF) имеет значение по умолчанию *стиль ссылки* , использующий имя поставщика и серийный номер, если в сертификате отсутствует расширение SKI.</span><span class="sxs-lookup"><span data-stu-id="0c395-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="0c395-107">Если в сертификате имеется расширение идентификатора ключа субъекта (SKI), стиль ссылки по умолчанию использует его для указания на сертификат.</span><span class="sxs-lookup"><span data-stu-id="0c395-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="0c395-108">Если в процессе разработки приложения, выполняется переход с сертификатов, не использующих расширение SKI на сертификаты, использующие данное расширение, стиль ссылки, используемые в сообщениях, созданных WCF также изменяется.</span><span class="sxs-lookup"><span data-stu-id="0c395-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="0c395-109">Если требуется согласованный стиль ссылки независимо от наличия расширения идентификатора ключа субъекта (SKI), необходимый стиль ссылки можно настроить, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0c395-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c395-110">Пример</span><span class="sxs-lookup"><span data-stu-id="0c395-110">Example</span></span>  
 <span data-ttu-id="0c395-111">В следующем примере кода создается пользовательский элемент привязки безопасности, использующий единый согласованный стиль ссылки с именем издателя и серийным номером.</span><span class="sxs-lookup"><span data-stu-id="0c395-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0c395-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0c395-112">Compiling the Code</span></span>  
 <span data-ttu-id="0c395-113">Для компиляции кода требуются следующие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0c395-113">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="0c395-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0c395-114">See Also</span></span>  
 [<span data-ttu-id="0c395-115">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0c395-115">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
