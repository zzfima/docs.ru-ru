---
title: Ресурсы операционной системы, необходимые WCF
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: c2c26d769424a8d0655591cb10b4b13df8a15884
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961134"
---
# <a name="operating-system-resources-required-by-wcf"></a>Ресурсы операционной системы, необходимые WCF

Windows Communication Foundation (WCF) зависит от нескольких ресурсов, предоставляемых операционной системой для работы. В следующей таблице перечислены эти ресурсы.

|Ресурс|Описание|
|--------------|-----------------|
|Координатор распределенных транзакций (Майкрософт)|Требуется для поддержки транзакций OleTx.|
|службы IIS|Требуется, если необходимо использовать службы IIS для размещения приложения.|
|Служба активации Windows (WAS)|Требуется, если необходимо использовать WAS для размещения приложения.|
