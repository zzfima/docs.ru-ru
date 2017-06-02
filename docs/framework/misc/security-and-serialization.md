---
title: "Security and Serialization | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "code security, serialization"
  - "serialization, security"
  - "secure coding, serialization"
  - "security [.NET Framework], serialization"
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Security and Serialization
Поскольку сериализация может разрешить другому коду просматривать или изменять данные экземпляра объекта, которые могут быть недоступны другим способом, требуется специальное разрешение кода, выполняющего сериализацию: <xref:System.Security.Permissions.SecurityPermission> с указанным флагом <xref:System.Security.Permissions.SecurityPermissionFlag>. При политике безопасности по умолчанию такое разрешение не предоставляется коду, загруженному из Интернета или интрасети, и дается только коду на локальном компьютере.  
  
 Как правило, сериализуются все поля экземпляра объекта; это означает, что данные представлены в сериализованных данных для экземпляра. Код, который может интерпретировать формат, может определять значения данных, независимо от доступности члена. Аналогично, десериализация извлекает данные из сериализованного представления и задает состояние объекта напрямую, снова независимо от правил специальных возможностей.  
  
 Объект, содержащий важные для обеспечения безопасности данные, следует по возможности делать несериализуемым. Если он должен быть сериализуемым, попробуйте сделать специальные поля хранения конфиденциальных данных несериализуемыми. Если это сделать нельзя, помните, что эти данные будут предоставлены любому коду, имеющему разрешение на сериализацию, и убедитесь, что вредоносный код не может получить это разрешение.  
  
 Интерфейс <xref:System.Runtime.Serialization.ISerializable> предназначен для использования только инфраструктурой сериализации. Однако если он не защищен, то потенциально может раскрыть конфиденциальные сведения. Если вы обеспечиваете настраиваемую сериализацию путем реализации **ISerializable**, убедитесь, что вы приняли следующие меры предосторожности.  
  
-   Вы должны явно защитить метод <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>, либо требуя **SecurityPermission** с указанным разрешением **SerializationFormatter**, либо убедившись, что никакие конфиденциальные сведения не раскрываются в выходных данных метода. Например:  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _ Sub GetObjectData(info As SerializationInfo, context As StreamingContext) End Sub  
  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter =true)] public override void GetObjectData(SerializationInfo info, StreamingContext context) { }  
    ```  
  
-   Специальный конструктор, используемый для сериализации, также должен выполнять тщательную проверку входных данных и должен быть либо защищенным, либо закрытым, чтобы предотвратить несанкционированное использование вредоносным кодом. Следует обеспечить те же проверки безопасности и разрешения, необходимые для получения экземпляра подобного класса любыми другими методами, например путем явного создания класса или его неявного создания через какую\-либо фабрику.  
  
## См. также  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)