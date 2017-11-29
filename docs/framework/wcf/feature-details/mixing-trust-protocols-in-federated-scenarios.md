---
title: "Использование нескольких протоколов доверия в сценариях федерации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 007dec81766423ea2826e98ae0b6b399a1508f11
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Использование нескольких протоколов доверия в сценариях федерации
Возможны сценарии, в которых федеративные клиенты взаимодействуют со службой и службой маркеров безопасности, версии доверия которых не совпадают. Код WSDL службы может содержать утверждение `RequestSecurityTokenTemplate` с элементами WS-Trust, версии которых не совпадают с версией службы маркеров безопасности. В этих случаях клиент [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] преобразует элементы WS-Trust, полученные из `RequestSecurityTokenTemplate`, для соответствия версии STS trust. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает несовпадающие версии trust только для стандартных привязок. Все стандартные параметры алгоритмов, распознаваемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], являются частью стандартной привязки. В этом разделе описано поведение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с различными параметрами доверия для службы и службы маркеров безопасности.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>Проверяющая сторона и служба маркеров безопасности используют версию февраля 2005 г.  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 Среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не различает параметры клиента и службы; она добавляет все параметры и отправляет их в `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>Проверяющая сторона и служба маркеров безопасности используют версию Trust 1.3  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 Файл конфигурации клиента содержит элемент `secondaryParameters`, являющийся оболочкой для параметров, заданных проверяющей стороной.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] удаляет элементы `EncryptionAlgorithm`, `CanonicalizationAlgorithm` и `KeyWrapAlgorithm` из элемента верхнего уровня под RST, если они присутствуют внутри элемента `SecondaryParameters`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] добавляет элемент `SecondaryParameters` в исходящий шаблон RST без изменений.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>Проверяющая сторона использует версию февраля 2005 г., а служба маркеров безопасности - версию Trust 1.3  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 В файле конфигурации клиента среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не различает параметры клиента и службы. Поэтому среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] преобразует все параметры к пространству имен Trust 1.3.  
  
 Среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает элементы `KeyType`, `KeySize` и `TokenType` следующим образом.  
  
-   Загружается код WSDL, создается привязка и присваиваются значения `KeyType`, `KeySize` и `TokenType` на основании параметров проверяющей стороны. Создается файл конфигурации клиента.  
  
-   Теперь клиент может изменять любые параметры в файле конфигурации.  
  
-   Во время выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] копирует все заданные параметры в раздел `AdditionalTokenParameters` файла конфигурации клиента, кроме параметров `KeyType`, `KeySize` и `TokenType`, поскольку эти параметры учитываются во время создания файла конфигурации.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>Проверяющая сторона использует версию Trust 1.3, а служба маркеров безопасности - версию февраля 2005 г.  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 Файл конфигурации клиента содержит элемент `secondaryParamters`, являющийся оболочкой для параметров, заданных проверяющей стороной.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] копирует все параметры, задаваемые в разделе `SecondaryParameters` в элемент RST верхнего уровня, но не преобразует их в пространство имен WS-Trust 2005.
