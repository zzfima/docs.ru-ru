---
title: "JSONP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# JSONP
В этом образце показано, как обеспечить поддержку JSONP\(JSON with Padding\) в службах WCF REST.  JSONP является правилом, используемым для вызова скриптов между доменами путем создания тегов скриптов в текущем документе.  Результат возвращается в заданной функции обратного вызова.  JSONP основан на идее, что теги, такие как \<script src\=”http:\/\/...” \> могут выполнять скрипты из любого домена, причем скрипт, полученный этими тегами, выполняется в области, где уже могут быть определены другие функции.  
  
## Демонстрации  
 Междоменная работа со скриптами с JSONP.  
  
## Обсуждение  
 В образец входит веб\-страница, которая динамически добавляет блок скрипта после отображения страницы в веб\-браузере.  В этом блоке скрипта вызывается служба WCF REST, содержащая одну операцию `GetCustomer`.  Служба WCF REST возвращает имя и адрес клиента, заключенные в оболочку функции обратного вызова.  Когда служба WCF REST отправляет ответ, вызывается функция обратного вызова на веб\-странице с данными о клиенте, и функция обратного вызова выводит эти данные на веб\-странице.  Вставка тега скрипта и выполнение функции обратного вызова автоматически обрабатываются элементом управления ASP.NET AJAX ScriptManager.  Схема использования та же, что и для всех прокси ASP.NET AJAX, плюс добавляется строка для включения JSONP, как показано в следующем коде.  
  
```csharp  
var proxy = new JsonpAjaxService.CustomerService();  
proxy.set_enableJsonp(true);  
proxy.GetCustomer(onSuccess, onFail, null);  
  
```  
  
 Веб\-страница может вызывать службу WCF REST, поскольку эта служба использует объект <xref:System.ServiceModel.Description.WebScriptEndpoint>, где свойство `crossDomainScriptAccessEnabled` установлено в значении `true`.  Обе операции настройки выполняются в файле Web.config в элементе \<system.serviceModel\>.  
  
```  
<system.serviceModel>  
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 ScriptManager управляет взаимодействием со службой и устраняет сложности реализации доступа JSONP вручную.  Если `crossDomainScriptAccessEnabled` имеет значение `true`, а операция имеет формат ответа JSON, то инфраструктура [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет URI запроса для строкового параметра запроса обратного вызова и заключает ответ JSON в значение строкового параметра запроса обратного вызова.  В образце веб\-страница вызывает службу WCF REST со следующим URI.  
  
```  
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0  
  
```  
  
 Поскольку строковый параметр запроса обратного вызова имеет значение `JsonPCallback`, служба WCF возвращает ответ JSONP, показанный в следующем примере.  
  
```  
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});  
  
```  
  
 Этот ответ JSONP содержит данные о клиенте в формате JSON, заключенные в имя функции обратного вызова, запрошенной веб\-страницей.  ScriptManager будет выполнять этот обратный вызов, используя тег скрипта для междоменного запроса, а затем передаст результат в обработчик onSuccess, который передан в операцию GetCustomer прокси ASP.NET AJAX.  
  
 Образец состоит из двух веб\-приложений ASP.NET: одно содержит только службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а другое содержит веб\-страницу ASPX, которая вызывает службу.  Во время работы решения [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] размещает два веб\-сайта по различным портам, и создается среда, где служба и клиент работают в различных доменах.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### Выполнение образца  
  
1.  Откройте решение для образца JSONP.  
  
2.  Нажмите клавишу F5, чтобы запустить http:\/\/localhost:26648\/JSONPClientPage.aspx в браузере.  
  
3.  Заметьте, что после загрузки страницы поля ввода для имени и адреса заполняются значениями.  Эти значения получены из вызова службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] после того, как браузер завершил визуализацию страницы.