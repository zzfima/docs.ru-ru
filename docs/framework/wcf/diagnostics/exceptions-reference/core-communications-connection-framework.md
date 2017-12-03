---
title: "Основное взаимодействие: структура подключения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 878d2b01ee22d339115925e101f7349ecd5207bd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-connection-framework"></a>Основное взаимодействие: структура подключения
В этом разделе перечислены все исключения, вызываемые структурой подключения [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|CloseTimedOut|Срок ожидания метода Close истек по прошествии заданного времени. Увеличьте время ожидания, передаваемое вызову метода Close, или увеличьте значение CloseTimeout в привязке. Возможно, выделенное для этой операции время было частью более длительного времени ожидания.|  
|ContentTypeMismatch|Указанный тип контента был отправлен службе, которая ожидала указанный. Возможно несоответствие привязок клиента и службы.|  
|DuplexChannelAbortedDuringOpen|Дуплексный канал к указанному был закрыт во время процесса Open.|  
|FramingValueNotAvailable|Доступ к значению невозможен, так как оно не было полностью декодировано.|  
|OperationAbortedDuringConnectionEstablishment|Операция была прервана во время установления подключения к указанному.|  
|ReceiveTimedOut2|Срок ожидания операции получения истек по прошествии заданного времени. Возможно, выделенное для этой операции время было частью более длительного времени ожидания.|  
|SendCannotBeCalledAfterCloseOutputSession|Отправка сообщений по каналу после вызова метода CloseOutputSession невозможна.|
