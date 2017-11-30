---
title: MSMQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fca29f-fa44-4ec4-bb48-b10800694500
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a827cc89917a26552c77dc742cb12aa2d49d1d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="msmq"></a>MSMQ
В приложениях MSMQ никакие дополнительные действия не передаются из очереди канала в MSMQ и обратно.  
  
 Кроме того, в рамках трассировки очереди канала во время операции Send отслеживаются идентификатор сообщения MSMQ, идентификатор сообщения SOAP (а также идентификатор действия, если он существует).  
  
 Идентификатор сообщения MSMQ, идентификатор сообщения SOAP (а также идентификатор действия, если он существует) отслеживаются в рамках трассировки очереди канала во время операции Receive.  
  
 Необходимые действия по передаче во время операции Receive выполняются так же, как при любом другом транспорте (получение данных -> обработка сообщения -> операция).
