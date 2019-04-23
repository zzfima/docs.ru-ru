---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 3745c542986d405312a308fcf50ba6d7b6f93a1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074187"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="3db1e-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="3db1e-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="3db1e-103">Сбой службы протокола WS-AT при отправке сообщения Register своему координатору</span><span class="sxs-lookup"><span data-stu-id="3db1e-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="3db1e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="3db1e-104">Description</span></span>  
 <span data-ttu-id="3db1e-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager по причине невозможности отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="3db1e-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3db1e-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="3db1e-106">Troubleshooting</span></span>  
 <span data-ttu-id="3db1e-107">Проверить сообщение трассировки на исключение, приводящее к сбою отправки сообщения</span><span class="sxs-lookup"><span data-stu-id="3db1e-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db1e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3db1e-108">See also</span></span>

- [<span data-ttu-id="3db1e-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="3db1e-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="3db1e-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="3db1e-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3db1e-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="3db1e-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
