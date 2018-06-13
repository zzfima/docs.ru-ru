---
title: 'Основное взаимодействие: структура подключения'
ms.date: 03/30/2017
ms.assetid: 61ee00e1-896d-47c8-942f-1db28ac89cdc
ms.openlocfilehash: a3f52ac82c2bf09ded504e412d7f216dd0b39959
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471980"
---
# <a name="core-communications-connection-framework"></a>Основное взаимодействие: структура подключения
В этом разделе перечислены все исключения, вызываемые структурой подключения Windows Communication Foundation (WCF).  
  
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
