---
title: "Создание подписанного и/или зашифрованного пользовательского заголовка | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Создание подписанного и/или зашифрованного пользовательского заголовка
При вызове службы, которая не является службой WCF, с помощью клиента WCF иногда приходится применять пользовательские заголовки протокола SOAP.  В WCF имеется ошибка канонизации, которая не позволяет подписанным и зашифрованным пользовательским заголовкам работать со службами, не являющимися службами WCF.  Проблема вызывается неверной канонизацией пространств имен XML по умолчанию.  Она возникает только при вызове служб, не являющихся службами WCF, с подписанными и\/или зашифрованными пользовательскими заголовками.  Когда служба получает сообщение, содержащее подписанный и\/или зашифрованный пользовательский заголовок, ей не удается проверить сигнатуру.  Данный обходный путь решения проблемы обходит проблему канонизации, позволяет работать со службами, которые не являются службами WCF, но не мешает работать и со службами WCF.  
  
## Определение пользовательского заголовка  
 Пользовательские заголовки определяются посредством определения контракта сообщения и отметки элементов, которые должны отправляться в форме заголовков, атрибутом <xref:System.ServiceModel.MessageHeaderAttribute>.  Чтобы обойти ошибку канонизации, необходимо, чтобы сериализатор XML объявлял пространство имен в пользовательском заголовке с помощью префикса вместо объявления пространства имен по умолчанию.  В коде ниже показывается определение типа данных, который будет использоваться в качестве заголовка сообщения, с правильным объявлением пространства имен.  
  
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
  
 Этот код объявляет новый тип, `msgHeaderElement`, который будет сериализоваться с помощью сериализатора XML.  Когда экземпляр данного типа сериализуется, он будет определять пространство имен с префиксом «h», тем самым обходя ошибку канонизации.  Затем контракт сообщения определяет экземпляр `msgHeaderElement` и отмечает его атрибутом <xref:System.ServiceModel.MessageHeaderAttribute>, как показано в следующем примере.  
  
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
  
## См. также  
 [Контракт сообщения по умолчанию](../../../../docs/framework/wcf/samples/default-message-contract.md)   
 [Контракты сообщений](../../../../docs/framework/wcf/samples/message-contracts.md)   
 [Использование контрактов сообщений](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)