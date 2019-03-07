---
title: 1004 ― WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485191"
---
# <a name="1004---workflowinstanceaborted"></a>1004 ― WorkflowInstanceAborted

## <a name="properties"></a>Свойства

|||
|-|-|
|Идентификатор|1004|
|Ключевые слова|WFRuntime|
|Уровень|Сведения|
|Канал|Microsoft-Windows-Application Server-Applications/Debug|

## <a name="description"></a>Описание:

Указывает, что экземпляр рабочего процесса был прерван с исключением.

## <a name="message"></a>Сообщение

Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.

## <a name="details"></a>Подробные сведения

|Имя элемента данных|Тип элемента данных|Описание|
|--------------------|--------------------|-----------------|
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|
|Исключение|`xs:string`|Сведения об исключении|
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
