---
title: Асинхронные сценарии с использованием HTTP, TCP или именованного канала
ms.date: 03/30/2017
ms.assetid: a4d62402-43a4-48a4-9ced-220633ebc4ce
ms.openlocfilehash: 48957ec0abd1b4b0623f9b613fcd94912a38845b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881734"
---
# <a name="asynchronous-scenarios-using-http-tcp-or-named-pipe"></a>Асинхронные сценарии с использованием HTTP, TCP или именованного канала
В этом разделе описываются действия и перенаправления для различных асинхронных сценариев типа запрос-ответ (с многопотоковыми запросами с использованием HTTP, TCP или именованного канала).  
  
## <a name="asynchronous-requestreply-without-errors"></a>Асинхронный запрос-ответ без ошибок  
 В этом разделе описываются действия и перенаправления для асинхронного сценария типа запрос-ответ (с многопотоковым клиентом).  
  
 Действие вызывающего завершается, когда возвращается значение `beginCall` и `endCall`. При осуществлении обратного вызова возвращается обратный вызов.  
  
 Вызываемое действие завершится, когда возвращается значение `beginCall` и `endCall` или когда возвращается обратный вызов, если он был вызван из данного действия.  
  
### <a name="asynchronous-client-without-callback"></a>Асинхронный клиент без обратного вызова  
  
#### <a name="propagation-is-enabled-on-both-sides-using-http"></a>Распространение включено для обеих сторон (с использованием HTTP)  
 ![Асинхронный клиент с без обратного вызова, где propagateActivity имеет значение true на обеих сторонах.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-no-callback.gif)   
  
 Если `propagateActivity` = `true`, действие ProcessMessage указывает, какое действие ProcessAction для передачи.  
  
 Для сценариев, основанных на HTTP, для первого отправляемого сообщения вызывается действие ReceiveBytes, которое сохраняется на время существования запроса.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-http"></a>Распространение отключено для обеих сторон (с использованием HTTP)  
 Если `propagateActivity` = `false` с обеих сторон, действие ProcessMessage указывает, какое действие processaction должно быть для. Таким образом, вызывается новое временное действие ProcessAction с новым идентификатором. Если асинхронный ответ соответствует запросу в коде ServiceModel, идентификатор действия может быть получен из локального контекста. Фактическое действие ProcessAction может быть передано с данным идентификатором.  
  
 ![Асинхронный клиент без обратного вызова, где propagateActivity имеет значение false с обеих сторон.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-either-side.gif)  
    
 Для сценариев, основанных на HTTP, для первого отправляемого сообщения вызывается действие ReceiveBytes, которое сохраняется на время существования запроса.  
  
 Действие Process Action создается на асинхронном клиенте при `propagateActivity` = `false` в вызывающей или вызываемой и когда ответное сообщение не содержит заголовка Action.  
  
#### <a name="propagation-is-enabled-on-both-sides-using-tcp-or-named-pipe"></a>Распространение включено для обеих сторон (с использованием TCP или именованного канала)  
 ![Асинхронный клиент с без обратного вызова, propagateActivity которых имеет значение true на обеих сторонах и именованного канала или TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-enabled-using-tcp.gif)  
  
 Для сценария, основанного на именованном канале или TCP, действие ReceiveBytes вызывается при открытии клиента и сохраняется на время существования подключения.  
  
 Аналогично первому изображению, если `propagateActivity` = `true`, действие ProcessMessage указывает, какое действие ProcessAction для передачи.  
  
#### <a name="propagation-is-disabled-on-either-sides-using-tcp-or-named-pipe"></a>Распространение отключено для обеих сторон (с использованием TCP или именованного канала)  
 Для сценария, основанного на именованном канале или TCP, действие ReceiveBytes вызывается при открытии клиента и сохраняется на время существования подключения.  
  
 Аналогичную второе изображение, если `propagateActivity` = `false` с обеих сторон, действие ProcessMessage указывает, какое действие processaction должно быть для. Таким образом, вызывается новое временное действие ProcessAction с новым идентификатором. Если асинхронный ответ соответствует запросу в коде ServiceModel, идентификатор действия может быть получен из локального контекста. Фактическое действие ProcessAction может быть передано с данным идентификатором.  
  
 ![Асинхронный клиент без обратного вызова, где propagateActivity — значение false с обеих сторон, а с именем именованного канала или TCP.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-scenario-propagation-disabled-using-tcp.gif)  
    
### <a name="asynchronous-client-with-callback"></a>Асинхронный клиент с обратным вызовом  
 В данном сценарии добавляются действия G и A’ для обратного вызова и `endCall`, а также их передачи в обратном вызове и вне его.  
  
 В этом разделе показано только использование HTTP с `propragateActivity` = `true`. Однако дополнительные действия и передачи также применимы к другим случаям (то есть `propagateActivity` = `false`, с использованием TCP или именованного канала).  
  
 Обратный вызов создает новое действие (G), когда клиент вызывает пользовательский код для уведомления о готовности результатов. Затем пользовательский код вызывает `endCall` в обратном вызове (как показано на рисунке 5) или вне обратного вызова (рисунок 6). Так как неизвестно, какое действие пользователя `endCall` вызывается, это действие помечается буквой `A’`. Действие A’ может быть одинаковым или отличаться от действия A.  
  
 ![Показывает асинхронный клиент с обратным вызовом, endcall внутри обратного вызова.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-in-callback.gif)  
    
 ![Показывает асинхронный клиент с обратным вызовом, endcall вне обратного вызова.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-client-callback-endcall-outside-callback.gif)  
    
### <a name="asynchronous-server-with-callback"></a>Асинхронный сервер с обратным вызовом  
 ![Показывает асинхронный сервер с обратным вызовом.](./media/asynchronous-scenarios-using-http-tcp-or-named-pipe/asynchronous-server-callback.gif)  
    
 Стек каналов выполняет обратный вызов клиента при получении сообщения: трассировки для данной обработки выдаются в самом действии ProcessRequest.  
  
## <a name="asynchronous-requestreply-with-errors"></a>Асинхронный запрос-ответ с ошибками  
 Во время `endCall` получаются сообщения об ошибке. В противном случае действия и передачи аналогичны предыдущим сценариям.  
  
## <a name="asynchronous-one-way-with-or-without-errors"></a>Асинхронная односторонняя связь с ошибками или без них  
 Ответ отсутствует или клиенту возвращается ошибка.
