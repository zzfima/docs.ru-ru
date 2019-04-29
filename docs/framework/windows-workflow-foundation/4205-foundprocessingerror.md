---
title: 4205 - FoundProcessingError
ms.date: 03/30/2017
ms.assetid: f2235a15-dd87-439e-8cb9-8b1b89a3dacf
ms.openlocfilehash: 732632ddc9a7712169ace984c1d6d0098a7ae608
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774339"
---
# <a name="4205---foundprocessingerror"></a>4205 - FoundProcessingError
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|4205|  
|Ключевые слова|WFInstanceStore|  
|Уровень|Error|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает на сбой команды поставщика SQL.  
  
## <a name="message"></a>Сообщение  
 Не удалось выполнить команду: %1  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|Текст сообщения из исключения SQL.|  
|Исключение|xs:string|Сведения об исключении|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
