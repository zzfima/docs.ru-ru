---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.date: 03/30/2017
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
ms.openlocfilehash: 947391e0594ffddba8235c519a076d330b73d4d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632638"
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a><span data-ttu-id="05d29-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="05d29-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span></span>
<span data-ttu-id="05d29-103">Невозможно создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="05d29-103">A transaction could not be created.</span></span>  
  
## <a name="description"></a><span data-ttu-id="05d29-104">Описание</span><span class="sxs-lookup"><span data-stu-id="05d29-104">Description</span></span>  
 <span data-ttu-id="05d29-105">Данная трассировка создается, если MSDTC не может создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="05d29-105">This trace is generated when MSDTC is unable to create a transaction.</span></span> <span data-ttu-id="05d29-106">Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.</span><span class="sxs-lookup"><span data-stu-id="05d29-106">This can be due to low resources, insufficient log space, or other errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="05d29-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="05d29-107">Troubleshooting</span></span>  
 <span data-ttu-id="05d29-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="05d29-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d29-109">См. также</span><span class="sxs-lookup"><span data-stu-id="05d29-109">See also</span></span>
- [<span data-ttu-id="05d29-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="05d29-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="05d29-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="05d29-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="05d29-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="05d29-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
