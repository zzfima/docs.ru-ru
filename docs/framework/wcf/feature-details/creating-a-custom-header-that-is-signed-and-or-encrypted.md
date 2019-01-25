---
title: Создание пользовательского заголовка, который подписан и- шифрованные
ms.date: 03/30/2017
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
ms.openlocfilehash: 0f8f86bcb5494cd502d14aff1cf3c4cdf4f8dd33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494825"
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a><span data-ttu-id="ab9d0-102">Создание пользовательского заголовка, который подписан и- шифрованные</span><span class="sxs-lookup"><span data-stu-id="ab9d0-102">Creating a custom header that is signed and-or encrypted</span></span>
<span data-ttu-id="ab9d0-103">При вызове службы, которая не является службой WCF, с помощью клиента WCF иногда приходится применять пользовательские заголовки протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-103">When calling a non-WCF service using a WCF client it is sometimes necessary to use custom SOAP headers.</span></span> <span data-ttu-id="ab9d0-104">В WCF имеется ошибка канонизации, которая не позволяет подписанным и зашифрованным пользовательским заголовкам работать со службами, не являющимися службами WCF.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-104">There is a canonicalization bug in WCF that prevents custom headers that are signed and encrypted from working with a non-WCF service.</span></span> <span data-ttu-id="ab9d0-105">Проблема вызывается неверной канонизацией пространств имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-105">The problem is caused by the incorrect canonicalization of default XML namespaces.</span></span> <span data-ttu-id="ab9d0-106">Она возникает только при вызове служб, не являющихся службами WCF, с подписанными и/или зашифрованными пользовательскими заголовками.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-106">This is only problematic when calling non-WCF services with custom headers that are signed and/or encrypted.</span></span>  <span data-ttu-id="ab9d0-107">Когда служба получает сообщение, содержащее подписанный и/или зашифрованный пользовательский заголовок, ей не удается проверить сигнатуру.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-107">When the service receives the message containing the signed and/or encrypted custom header it is unable to verify the signature.</span></span> <span data-ttu-id="ab9d0-108">Данный обходный путь решения проблемы обходит проблему канонизации, позволяет работать со службами, которые не являются службами WCF, но не мешает работать и со службами WCF.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-108">This workaround avoids the canonicalization bug, allows interoperability with non-WCF services, but does not prevent interoperability with WCF services.</span></span>  
  
## <a name="defining-the-custom-header"></a><span data-ttu-id="ab9d0-109">Определение пользовательского заголовка</span><span class="sxs-lookup"><span data-stu-id="ab9d0-109">Defining the custom header</span></span>  
 <span data-ttu-id="ab9d0-110">Пользовательские заголовки определяются посредством определения контракта сообщения и отметки элементов, которые должны отправляться в форме заголовков, атрибутом <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-110">Custom headers are defined by defining a message contract and marking the members you want to be sent as headers with a <xref:System.ServiceModel.MessageHeaderAttribute> attribute.</span></span> <span data-ttu-id="ab9d0-111">Чтобы обойти ошибку канонизации, необходимо, чтобы сериализатор XML объявлял пространство имен в пользовательском заголовке с помощью префикса вместо объявления пространства имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-111">To work around the canonicalization bug you must ensure that the XML serializer declares the namespace for the custom header with a prefix instead of a default namespace declaration.</span></span> <span data-ttu-id="ab9d0-112">В коде ниже показывается определение типа данных, который будет использоваться в качестве заголовка сообщения, с правильным объявлением пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-112">The following code shows how to define the data type that will be used as a message header with the correct namespace declaration.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("svcutil", "3.0.4506.648")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://www.example.org/getMessage/")]  
public partial class msgHeaderElement  
{  
   // Define the XML namespace and force it to use an ‘h’ prefix  
    [System.Xml.Serialization.XmlNamespaceDeclarations]  
    public System.Xml.Serialization.XmlSerializerNamespaces _xsns = new System.Xml.Serialization.XmlSerializerNamespaces(new System.Xml.XmlQualifiedName[] { new System.Xml.XmlQualifiedName("h", "http://www.example.org/getMessage/") });  
  
    private string msgHeaderInputField;  
  [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified, Order=0)]  
    public string msgHeaderInput  
    {  
        get  
        {  
            return this.msgHeaderInputField;  
        }  
        set  
        {  
            this.msgHeaderInputField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="ab9d0-113">Этот код объявляет новый тип, `msgHeaderElement`, который будет сериализоваться с помощью сериализатора XML.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-113">This code declares a new type called `msgHeaderElement` that will be serialized with the XML Serializer.</span></span> <span data-ttu-id="ab9d0-114">Когда экземпляр данного типа сериализуется, он будет определять пространство имен с префиксом «h», тем самым обходя ошибку канонизации.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-114">When an instance of this type is serialized, it will define a namespace with an ‘h’ prefix, thus working around the canonicalization bug.</span></span>  <span data-ttu-id="ab9d0-115">Затем контракт сообщения определяет экземпляр `msgHeaderElement` и отмечает его атрибутом <xref:System.ServiceModel.MessageHeaderAttribute>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ab9d0-115">The message contract would then define an instance of `msgHeaderElement` and mark it with the <xref:System.ServiceModel.MessageHeaderAttribute> attribute as shown in the following example.</span></span>  
  
```  
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab9d0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ab9d0-116">See also</span></span>
- [<span data-ttu-id="ab9d0-117">Контракт сообщения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ab9d0-117">Default Message Contract</span></span>](../../../../docs/framework/wcf/samples/default-message-contract.md)
- [<span data-ttu-id="ab9d0-118">Контракты сообщений</span><span class="sxs-lookup"><span data-stu-id="ab9d0-118">Message Contracts</span></span>](../../../../docs/framework/wcf/samples/message-contracts.md)
- [<span data-ttu-id="ab9d0-119">Использование контрактов сообщений</span><span class="sxs-lookup"><span data-stu-id="ab9d0-119">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
