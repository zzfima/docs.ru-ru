---
title: Использование нескольких протоколов доверия в сценариях федерации
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: bca23ba16c69c6d21ed7cf49aaebb8d2ed079f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494471"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Использование нескольких протоколов доверия в сценариях федерации
Возможны сценарии, в которых федеративные клиенты взаимодействуют со службой и службой маркеров безопасности, версии доверия которых не совпадают. Код WSDL службы может содержать утверждение `RequestSecurityTokenTemplate` с элементами WS-Trust, версии которых не совпадают с версией службы маркеров безопасности. В таких случаях клиента Windows Communication Foundation (WCF) преобразует элементы WS-Trust, полученные от `RequestSecurityTokenTemplate` для соответствия версии STS trust. WCF обеспечивает версии несоответствующие доверия только для стандартных привязок. Все стандартные параметры алгоритмов, распознаваемые WCF являются частью стандартной привязки. В этом разделе описано поведение WCF с различными параметрами доверия между службой и STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>Проверяющая сторона и служба маркеров безопасности используют версию февраля 2005 г.  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 WCF не различает параметры клиента и службы; она добавляет все параметры и отправляет их `RequestSecurityTokenTemplate` (RST).  
  
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
  
 Удаляет WCF `EncryptionAlgorithm`, `CanonicalizationAlgorithm` и `KeyWrapAlgorithm` элементов из элемента верхнего уровня под RST, если они присутствуют внутри `SecondaryParameters` элемента. Добавляет WCF `SecondaryParameters` элемент в исходящий шаблон RST без изменений.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>Проверяющая сторона использует версию февраля 2005 г., а служба маркеров безопасности - версию Trust 1.3  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 В файле конфигурации клиента WCF не различает параметры клиента и службы. Поэтому WCF преобразует все параметры к пространству имен Trust версии 1.3.  
  
 Дескрипторы WCF `KeyType`, `KeySize`, и `TokenType` элементы следующим образом:  
  
-   Загружается код WSDL, создается привязка и присваиваются значения `KeyType`, `KeySize` и `TokenType` на основании параметров проверяющей стороны. Создается файл конфигурации клиента.  
  
-   Теперь клиент может изменять любые параметры в файле конфигурации.  
  
-   Во время выполнения, WCF копирует все заданные параметры в `AdditionalTokenParameters` раздел файла конфигурации клиента, за исключением `KeyType`, `KeySize` и `TokenType`, так как эти параметры учитываются во время создания файла конфигурации поколение.  
  
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
  
 WCF копирует все параметры, задаваемые в `SecondaryParameters` раздел в элемент RST верхнего уровня, но не преобразует их в пространство имен WS-Trust 2005.
