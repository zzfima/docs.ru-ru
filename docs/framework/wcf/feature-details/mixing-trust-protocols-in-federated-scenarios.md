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
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="c6ca9-102">Использование нескольких протоколов доверия в сценариях федерации</span><span class="sxs-lookup"><span data-stu-id="c6ca9-102">Mixing Trust Protocols in Federated Scenarios</span></span>
<span data-ttu-id="c6ca9-103">Возможны сценарии, в которых федеративные клиенты взаимодействуют со службой и службой маркеров безопасности, версии доверия которых не совпадают.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="c6ca9-104">Код WSDL службы может содержать утверждение `RequestSecurityTokenTemplate` с элементами WS-Trust, версии которых не совпадают с версией службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="c6ca9-105">В этих случаях клиент [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] преобразует элементы WS-Trust, полученные из `RequestSecurityTokenTemplate`, для соответствия версии STS trust.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-105">In such cases, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c6ca9-106"> обрабатывает несовпадающие версии trust только для стандартных привязок.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-106"> handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="c6ca9-107">Все стандартные параметры алгоритмов, распознаваемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], являются частью стандартной привязки.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-107">All standard algorithm parameters that are recognized by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are part of the standard binding.</span></span> <span data-ttu-id="c6ca9-108">В этом разделе описано поведение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с различными параметрами доверия для службы и службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-108">This topic describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="c6ca9-109">Проверяющая сторона и служба маркеров безопасности используют версию февраля 2005 г.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-109">RP Feb 2005 and STS Feb 2005</span></span>  
 <span data-ttu-id="c6ca9-110">Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="c6ca9-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="c6ca9-111">Файл конфигурации клиента содержит список параметров.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="c6ca9-112">Среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не различает параметры клиента и службы; она добавляет все параметры и отправляет их в `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="c6ca9-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="c6ca9-113">Проверяющая сторона и служба маркеров безопасности используют версию Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="c6ca9-113">RP Trust 1.3 and STS Trust 1.3</span></span>  
 <span data-ttu-id="c6ca9-114">Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="c6ca9-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="c6ca9-115">Файл конфигурации клиента содержит элемент `secondaryParameters`, являющийся оболочкой для параметров, заданных проверяющей стороной.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c6ca9-116"> удаляет элементы `EncryptionAlgorithm`, `CanonicalizationAlgorithm` и `KeyWrapAlgorithm` из элемента верхнего уровня под RST, если они присутствуют внутри элемента `SecondaryParameters`.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-116"> removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c6ca9-117"> добавляет элемент `SecondaryParameters` в исходящий шаблон RST без изменений.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-117"> appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="c6ca9-118">Проверяющая сторона использует версию февраля 2005 г., а служба маркеров безопасности - версию Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="c6ca9-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  
 <span data-ttu-id="c6ca9-119">Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="c6ca9-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 <span data-ttu-id="c6ca9-120">Файл конфигурации клиента содержит список параметров.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="c6ca9-121">В файле конфигурации клиента среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не различает параметры клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-121">From the client configuration file, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="c6ca9-122">Поэтому среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] преобразует все параметры к пространству имен Trust 1.3.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-122">Therefore [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="c6ca9-123">Среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обрабатывает элементы `KeyType`, `KeySize` и `TokenType` следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-123">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
-   <span data-ttu-id="c6ca9-124">Загружается код WSDL, создается привязка и присваиваются значения `KeyType`, `KeySize` и `TokenType` на основании параметров проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="c6ca9-125">Создается файл конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-125">The client configuration file is then generated.</span></span>  
  
-   <span data-ttu-id="c6ca9-126">Теперь клиент может изменять любые параметры в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-126">The client can now change any parameter in the configuration file.</span></span>  
  
-   <span data-ttu-id="c6ca9-127">Во время выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] копирует все заданные параметры в раздел `AdditionalTokenParameters` файла конфигурации клиента, кроме параметров `KeyType`, `KeySize` и `TokenType`, поскольку эти параметры учитываются во время создания файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-127">During runtime, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="c6ca9-128">Проверяющая сторона использует версию Trust 1.3, а служба маркеров безопасности - версию февраля 2005 г.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  
 <span data-ttu-id="c6ca9-129">Код WSDL проверяющей стороны содержит следующие элементы в разделе `RequestSecurityTokenTemplate`:</span><span class="sxs-lookup"><span data-stu-id="c6ca9-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 <span data-ttu-id="c6ca9-130">Файл конфигурации клиента содержит элемент `secondaryParamters`, являющийся оболочкой для параметров, заданных проверяющей стороной.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c6ca9-131"> копирует все параметры, задаваемые в разделе `SecondaryParameters` в элемент RST верхнего уровня, но не преобразует их в пространство имен WS-Trust 2005.</span><span class="sxs-lookup"><span data-stu-id="c6ca9-131"> copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
