---
title: Как выполнить Постоянно ссылку сертификатов X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: 2468faabfbca57e7d905a592b6743c43cb2ccd56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731976"
---
# <a name="how-to-consistently-reference-x509-certificates"></a>Как выполнить Постоянно ссылку сертификатов X.509
Существует несколько способов идентификации сертификата: с помощью хэша сертификата, имени поставщика и серийного номера, а также идентификатора ключа субъекта (SKI). Идентификатор ключа субъекта (SKI) обеспечивает уникальную идентификацию открытого ключа субъекта сертификата, поэтому он часто используется при работе с цифровой подписью XML. Значение SKI обычно является частью сертификата X.509 в виде *расширения сертификатов X.509*. Windows Communication Foundation (WCF) имеет значение по умолчанию *стиль ссылки* , использующий имя поставщика и серийный номер, если в сертификате отсутствует расширение SKI. Если в сертификате имеется расширение идентификатора ключа субъекта (SKI), стиль ссылки по умолчанию использует его для указания на сертификат. Если в процессе разработки приложения, выполняется переход с сертификатов, которые не имеют расширение SKI на сертификаты, использующие расширение SKI, стиль ссылки, используемые в сообщениях, созданный WCF также изменяется.  
  
 Если требуется согласованный стиль ссылки независимо от наличия расширения идентификатора ключа субъекта (SKI), необходимый стиль ссылки можно настроить, как показано в следующем примере кода.  
  
## <a name="example"></a>Пример  
 В следующем примере кода создается пользовательский элемент привязки безопасности, использующий единый согласованный стиль ссылки с именем издателя и серийным номером.  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для компиляции кода требуются следующие пространства имен.  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a>См. также
- [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
