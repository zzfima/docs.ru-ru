---
title: 1037 - RuntimeTransactionComplete
ms.date: 03/30/2017
ms.assetid: 2c8c31e0-42a9-4f46-865b-2da9ab16a0ba
ms.openlocfilehash: 7a94c917157904c5cb84105c41842657a534c973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1037---runtimetransactioncomplete"></a>1037 - RuntimeTransactionComplete
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1037|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает на завершение транзакции среды выполнения.  
  
## <a name="message"></a>Сообщение  
 Транзакция среды выполнения завершена с состоянием «%1».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Состояние|xs:string|Состояние транзакции.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
