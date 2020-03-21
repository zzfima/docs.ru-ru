---
title: Безопасность и сериализация
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, serialization
- serialization, security
- secure coding, serialization
- security [.NET Framework], serialization
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
ms.openlocfilehash: 634388e3920e0b9dbee85aa3ea555471cee604ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181121"
---
# <a name="security-and-serialization"></a><span data-ttu-id="96ad6-102">Безопасность и сериализация</span><span class="sxs-lookup"><span data-stu-id="96ad6-102">Security and Serialization</span></span>
<span data-ttu-id="96ad6-103">Поскольку сериализация может разрешить другому коду просматривать или изменять данные экземпляра объекта, которые могут быть недоступны другим способом, требуется специальное разрешение кода, выполняющего сериализацию: <xref:System.Security.Permissions.SecurityPermission> с указанным флагом <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> .</span><span class="sxs-lookup"><span data-stu-id="96ad6-103">Because serialization can allow other code to see or modify object instance data that would otherwise be inaccessible, a special permission is required of code performing serialization: <xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="96ad6-104">При политике безопасности по умолчанию такое разрешение не предоставляется коду, загруженному из Интернета или интрасети, и дается только коду на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="96ad6-104">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span>  
  
 <span data-ttu-id="96ad6-105">Как правило, сериализуются все поля экземпляра объекта; это означает, что данные представлены в сериализованных данных для экземпляра.</span><span class="sxs-lookup"><span data-stu-id="96ad6-105">Normally, all fields of an object instance are serialized, meaning that data is represented in the serialized data for the instance.</span></span> <span data-ttu-id="96ad6-106">Код, который может интерпретировать формат, может определять значения данных, независимо от доступности члена.</span><span class="sxs-lookup"><span data-stu-id="96ad6-106">It is possible for code that can interpret the format to determine what the data values are, independent of the accessibility of the member.</span></span> <span data-ttu-id="96ad6-107">Аналогично, десериализация извлекает данные из сериализованного представления и задает состояние объекта напрямую, снова независимо от правил специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="96ad6-107">Similarly, deserialization extracts data from the serialized representation and sets object state directly, again irrespective of accessibility rules.</span></span>  
  
 <span data-ttu-id="96ad6-108">Объект, содержащий важные для обеспечения безопасности данные, следует по возможности делать несериализуемым.</span><span class="sxs-lookup"><span data-stu-id="96ad6-108">Any object that could contain security-sensitive data should be made nonserializable, if possible.</span></span> <span data-ttu-id="96ad6-109">Если он должен быть сериализуемым, попробуйте сделать специальные поля хранения конфиденциальных данных несериализуемыми.</span><span class="sxs-lookup"><span data-stu-id="96ad6-109">If it must be serializable, try to make specific fields that hold sensitive data nonserializable.</span></span> <span data-ttu-id="96ad6-110">Если это сделать нельзя, помните, что эти данные будут предоставлены любому коду, имеющему разрешение на сериализацию, и убедитесь, что вредоносный код не может получить это разрешение.</span><span class="sxs-lookup"><span data-stu-id="96ad6-110">If this cannot be done, be aware that this data will be exposed to any code that has permission to serialize, and make sure that no malicious code can get this permission.</span></span>  
  
 <span data-ttu-id="96ad6-111">Интерфейс <xref:System.Runtime.Serialization.ISerializable> предназначен для использования только инфраструктурой сериализации.</span><span class="sxs-lookup"><span data-stu-id="96ad6-111">The <xref:System.Runtime.Serialization.ISerializable> interface is intended for use only by the serialization infrastructure.</span></span> <span data-ttu-id="96ad6-112">Однако если он не защищен, то потенциально может раскрыть конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="96ad6-112">However, if unprotected, it can potentially release sensitive information.</span></span> <span data-ttu-id="96ad6-113">Если вы обеспечиваете настраиваемую сериализацию путем реализации **ISerializable**, убедитесь, что вы приняли следующие меры предосторожности.</span><span class="sxs-lookup"><span data-stu-id="96ad6-113">If you provide custom serialization by implementing **ISerializable**, make sure you take the following precautions:</span></span>  
  
- <span data-ttu-id="96ad6-114">Вы должны явно защитить метод <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> , либо требуя **SecurityPermission** с указанным разрешением **SerializationFormatter** , либо убедившись, что никакие конфиденциальные сведения не раскрываются в выходных данных метода.</span><span class="sxs-lookup"><span data-stu-id="96ad6-114">The <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> method should be explicitly secured either by demanding the **SecurityPermission** with **SerializationFormatter** permission specified or by making sure that no sensitive information is released with the method output.</span></span> <span data-ttu-id="96ad6-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="96ad6-115">For example:</span></span>  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _  
    Sub GetObjectData(info As SerializationInfo, context As StreamingContext)  
    End Sub  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter
    =true)]  
    public override void GetObjectData(SerializationInfo info,
    StreamingContext context)  
    {  
    }  
    ```  
  
- <span data-ttu-id="96ad6-116">Специальный конструктор, используемый для сериализации, также должен выполнять тщательную проверку входных данных и должен быть либо защищенным, либо закрытым, чтобы предотвратить несанкционированное использование вредоносным кодом.</span><span class="sxs-lookup"><span data-stu-id="96ad6-116">The special constructor used for serialization should also perform thorough input validation and should be either protected or private to help protect against misuse by malicious code.</span></span> <span data-ttu-id="96ad6-117">Следует обеспечить те же проверки безопасности и разрешения, необходимые для получения экземпляра подобного класса любыми другими методами, например путем явного создания класса или его неявного создания через какую-либо фабрику.</span><span class="sxs-lookup"><span data-stu-id="96ad6-117">It should enforce the same security checks and permissions required to obtain an instance of such a class by any other means, such as explicitly creating the class or indirectly creating it through some kind of factory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ad6-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96ad6-118">See also</span></span>

- [<span data-ttu-id="96ad6-119">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="96ad6-119">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
