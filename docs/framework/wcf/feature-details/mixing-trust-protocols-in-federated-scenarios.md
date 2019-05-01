---
title: Использование нескольких протоколов доверия в сценариях федерации
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: ce5c3a1875d84d98068dcc78d8346a88bc0b28f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046696"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Использование нескольких протоколов доверия в сценариях федерации
Возможны сценарии, в которых федеративные клиенты взаимодействуют со службой и службой маркеров безопасности, версии доверия которых не совпадают. Код WSDL службы может содержать утверждение `RequestSecurityTokenTemplate` с элементами WS-Trust, версии которых не совпадают с версией службы маркеров безопасности. В таком случае клиент Windows Communication Foundation (WCF) преобразует элементы WS-Trust, полученные от `RequestSecurityTokenTemplate` в соответствии с версии STS trust. Платформа WCF выполняет версий несоответствующие trust только для стандартных привязок. Все стандартные параметры алгоритмов, распознаваемые WCF являются частью стандартной привязки. В этом разделе описано поведение WCF с различными параметрами доверия между службой и STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>Проверяющая сторона и служба маркеров безопасности используют версию февраля 2005 г.  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 WCF не различает параметры клиента и службы; он добавляет все параметры и отправляет их в `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>Проверяющая сторона и служба маркеров безопасности используют версию Trust 1.3  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Файл конфигурации клиента содержит элемент `secondaryParameters`, являющийся оболочкой для параметров, заданных проверяющей стороной.  
  
 Удаляет WCF `EncryptionAlgorithm`, `CanonicalizationAlgorithm` и `KeyWrapAlgorithm` элементов из элемента верхнего уровня под RST, если они присутствуют внутри `SecondaryParameters` элемент. Добавляет WCF `SecondaryParameters` элемент в исходящий шаблон RST без изменений.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>Проверяющая сторона использует версию февраля 2005 г., а служба маркеров безопасности - версию Trust 1.3  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 Файл конфигурации клиента содержит список параметров.  
  
 В файле конфигурации клиента WCF не различает параметры клиента и службы. Поэтому WCF преобразует все параметры к пространству имен Trust 1.3.  
  
 Дескрипторы WCF `KeyType`, `KeySize`, и `TokenType` элементы следующим образом:  
  
- Загружается код WSDL, создается привязка и присваиваются значения `KeyType`, `KeySize` и `TokenType` на основании параметров проверяющей стороны. Создается файл конфигурации клиента.  
  
- Теперь клиент может изменять любые параметры в файле конфигурации.  
  
- Во время выполнения, WCF копирует все заданные параметры в `AdditionalTokenParameters` раздел файла конфигурации клиента, за исключением `KeyType`, `KeySize` и `TokenType`, так как эти параметры учитываются во время создания файла конфигурации поколение.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>Проверяющая сторона использует версию Trust 1.3, а служба маркеров безопасности - версию февраля 2005 г.  
 Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 Файл конфигурации клиента содержит элемент `secondaryParamters`, являющийся оболочкой для параметров, заданных проверяющей стороной.  
  
 WCF копирует все параметры, задаваемые в `SecondaryParameters` раздел в элемент RST верхнего уровня, но не преобразует их в пространство имен WS-Trust 2005.
