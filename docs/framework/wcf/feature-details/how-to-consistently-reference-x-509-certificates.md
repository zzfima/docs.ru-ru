---
title: "Практическое руководство. Согласованное обращение к сертификатам X.509"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d42af919b9792fc5a5303737187be7ffef6405d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-consistently-reference-x509-certificates"></a>Практическое руководство. Согласованное обращение к сертификатам X.509
Существует несколько способов идентификации сертификата: с помощью хэша сертификата, имени поставщика и серийного номера, а также идентификатора ключа субъекта (SKI). Идентификатор ключа субъекта (SKI) обеспечивает уникальную идентификацию открытого ключа субъекта сертификата, поэтому он часто используется при работе с цифровой подписью XML. Данное значение обычно является частью сертификата X.509 в виде *расширения сертификатов X.509*. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]имеет значение по умолчанию *стиль ссылки* , использующий имя поставщика и серийный номер, если в сертификате отсутствует расширение SKI. Если в сертификате имеется расширение идентификатора ключа субъекта (SKI), стиль ссылки по умолчанию использует его для указания на сертификат. Если в процессе разработки приложения выполняется переход с сертификатов, не использующих расширение идентификатора ключа субъекта (SKI) на сертификаты, использующие данное расширение, изменяется также стиль ссылки по умолчанию, который используется в сообщениях, созданных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
 [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
