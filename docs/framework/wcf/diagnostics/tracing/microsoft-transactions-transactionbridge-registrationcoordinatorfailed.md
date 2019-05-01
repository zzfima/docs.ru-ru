---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 3745c542986d405312a308fcf50ba6d7b6f93a1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997780"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="2031c-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="2031c-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="2031c-103">Сбой службы протокола WS-AT при отправке сообщения Register своему координатору</span><span class="sxs-lookup"><span data-stu-id="2031c-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="2031c-104">Описание</span><span class="sxs-lookup"><span data-stu-id="2031c-104">Description</span></span>  
 <span data-ttu-id="2031c-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager по причине невозможности отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="2031c-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2031c-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="2031c-106">Troubleshooting</span></span>  
 <span data-ttu-id="2031c-107">Проверить сообщение трассировки на исключение, приводящее к сбою отправки сообщения</span><span class="sxs-lookup"><span data-stu-id="2031c-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2031c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2031c-108">See also</span></span>

- [<span data-ttu-id="2031c-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="2031c-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="2031c-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="2031c-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2031c-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="2031c-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
