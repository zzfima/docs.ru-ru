---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: 420686ebda7f23a5d883deece251b034147fafa4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654585"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="618f2-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="618f2-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="618f2-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="618f2-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="618f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="618f2-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="618f2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="618f2-105">Methods</span></span>  
 <span data-ttu-id="618f2-106">Класс ServiceBehaviorAttribute не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="618f2-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="618f2-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="618f2-107">Properties</span></span>  
 <span data-ttu-id="618f2-108">Класс ServiceBehaviorAttribute имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="618f2-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="618f2-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="618f2-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="618f2-110">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="618f2-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="618f2-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-112">Указывает, следует ли автоматически закрывать сеанс, когда клиент закрывает выходной сеанс.</span><span class="sxs-lookup"><span data-stu-id="618f2-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="618f2-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="618f2-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="618f2-114">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="618f2-114">Data type: string</span></span>  
<span data-ttu-id="618f2-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-116">Указывает, поддерживает служба один поток, несколько потоков или повторные входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="618f2-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="618f2-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="618f2-117">ConfigurationName</span></span>  
 <span data-ttu-id="618f2-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="618f2-118">Data type: string</span></span>  
  
 <span data-ttu-id="618f2-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-120">Имя конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="618f2-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="618f2-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="618f2-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="618f2-122">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="618f2-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="618f2-123">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-124">Указывает, требуется ли передать неизвестные данные сериализации по сети.</span><span class="sxs-lookup"><span data-stu-id="618f2-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="618f2-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="618f2-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="618f2-126">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="618f2-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="618f2-127">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-128">Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.</span><span class="sxs-lookup"><span data-stu-id="618f2-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="618f2-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="618f2-129">InstanceContextMode</span></span>  
 <span data-ttu-id="618f2-130">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="618f2-130">Data type: string</span></span>  
  
 <span data-ttu-id="618f2-131">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-132">Указывает, когда создается новый объект службы.</span><span class="sxs-lookup"><span data-stu-id="618f2-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="618f2-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="618f2-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="618f2-134">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="618f2-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="618f2-135">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-136">Максимальное количество элементов, допустимое в сериализованном объекте.</span><span class="sxs-lookup"><span data-stu-id="618f2-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="618f2-137">name</span><span class="sxs-lookup"><span data-stu-id="618f2-137">Name</span></span>  
 <span data-ttu-id="618f2-138">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="618f2-138">Data type: string</span></span>  
  
 <span data-ttu-id="618f2-139">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-140">Имя атрибута службы в WSDL.</span><span class="sxs-lookup"><span data-stu-id="618f2-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="618f2-141">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="618f2-141">Namespace</span></span>  
 <span data-ttu-id="618f2-142">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="618f2-142">Data type: string</span></span>  
  
 <span data-ttu-id="618f2-143">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-144">Целевое пространство имен службы в WSDL.</span><span class="sxs-lookup"><span data-stu-id="618f2-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="618f2-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="618f2-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="618f2-146">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="618f2-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="618f2-147">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-148">Указывает, производится ли повторное использование объекта службы после завершения текущей транзакции.</span><span class="sxs-lookup"><span data-stu-id="618f2-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="618f2-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="618f2-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="618f2-150">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="618f2-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="618f2-151">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-152">Указывает, завершаются ли ожидающие транзакции при закрытии текущего сеанса.</span><span class="sxs-lookup"><span data-stu-id="618f2-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="618f2-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="618f2-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="618f2-154">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="618f2-154">Data type: string</span></span>  
  
 <span data-ttu-id="618f2-155">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-156">Указывает уровень изоляции транзакции.</span><span class="sxs-lookup"><span data-stu-id="618f2-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="618f2-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="618f2-157">TransactionTimeout</span></span>  
 <span data-ttu-id="618f2-158">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="618f2-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="618f2-159">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-160">Период времени, в течение которого транзакция должна быть завершена.</span><span class="sxs-lookup"><span data-stu-id="618f2-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="618f2-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="618f2-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="618f2-162">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="618f2-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="618f2-163">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-164">Указывает, использовать ли текущий контекст синхронизации для выбора потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="618f2-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="618f2-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="618f2-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="618f2-166">Тип данных: boolean</span><span class="sxs-lookup"><span data-stu-id="618f2-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="618f2-167">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="618f2-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="618f2-168">Указывает, кем выполняется принудительная обработка заголовка SOAP MustUnderstand: системой или приложением.</span><span class="sxs-lookup"><span data-stu-id="618f2-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="618f2-169">Требования</span><span class="sxs-lookup"><span data-stu-id="618f2-169">Requirements</span></span>  
  
|<span data-ttu-id="618f2-170">MOF</span><span class="sxs-lookup"><span data-stu-id="618f2-170">MOF</span></span>|<span data-ttu-id="618f2-171">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="618f2-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="618f2-172">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="618f2-172">Namespace</span></span>|<span data-ttu-id="618f2-173">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="618f2-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="618f2-174">См. также</span><span class="sxs-lookup"><span data-stu-id="618f2-174">See also</span></span>
- <xref:System.ServiceModel.ServiceBehaviorAttribute>
