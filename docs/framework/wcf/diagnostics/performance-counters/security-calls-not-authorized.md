---
title: Неавторизованные вызовы системы безопасности
ms.date: 03/30/2017
ms.assetid: cb6acdcd-7336-42e1-9ae8-ac891336cd58
author: BrucePerlerMS
ms.openlocfilehash: 6af1c7576e6a0fe7ae21f6f1997b2ebe3b919214
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111910"
---
# <a name="security-calls-not-authorized"></a>Неавторизованные вызовы системы безопасности
Имя счетчика: Security Calls Not Authorized.  
  
## <a name="description"></a>Описание  
 Значение этого счетчика увеличивается, когда метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> возвращает значение `false`. Это показывает, что входящее сообщение было надлежащим образом защищено и поступило от допустимого пользователя, не авторизованного для выполнения определенных задач.
