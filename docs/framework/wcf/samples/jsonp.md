---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 82fa0bb09ebdf3ca2325872c2b884f4940de17ed
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715725"
---
# <a name="jsonp"></a>JSONP
В этом образце показано, как обеспечить поддержку JSONP(JSON with Padding) в службах WCF REST. JSONP является правилом, используемым для вызова скриптов между доменами путем создания тегов скриптов в текущем документе. Результат возвращается в заданной функции обратного вызова. JSONP основан на идее того, что такие теги, как `<script src="http://..." >`, могут оценивать скрипты из любого домена, а скрипт, полученный этими тегами, вычисляется в области, в которой уже могут быть определены другие функции.

## <a name="demonstrates"></a>Демонстрации
 Междоменная работа со скриптами с JSONP.

## <a name="discussion"></a>Обсуждение
 В образец входит веб-страница, которая динамически добавляет блок скрипта после отображения страницы в веб-браузере. В этом блоке скрипта вызывается служба WCF REST, содержащая одну операцию `GetCustomer`. Служба WCF REST возвращает имя и адрес клиента, заключенные в оболочку функции обратного вызова. Когда служба WCF REST отправляет ответ, вызывается функция обратного вызова на веб-странице с данными о клиенте, и функция обратного вызова выводит эти данные на веб-странице. Вставка тега скрипта и выполнение функции обратного вызова автоматически обрабатываются элементом управления ASP.NET AJAX ScriptManager. Схема использования та же, что и для всех прокси ASP.NET AJAX, плюс добавляется строка для включения JSONP, как показано в следующем коде.

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 Веб-страница может вызывать службу WCF REST, поскольку эта служба использует объект <xref:System.ServiceModel.Description.WebScriptEndpoint>, где свойство `crossDomainScriptAccessEnabled` установлено в значении `true`. Обе эти конфигурации выполняются в файле Web. config в элементе \<System. serviceModel >.

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 ScriptManager управляет взаимодействием со службой и устраняет сложности реализации доступа JSONP вручную. Если `crossDomainScriptAccessEnabled` имеет значение `true` и формат ответа для операции — JSON, инфраструктура WCF проверяет URI запроса на наличие параметра строки запроса обратного вызова и заключает ответ JSON в значение параметра строки запроса обратного вызова. В образце веб-страница вызывает службу WCF REST со следующим URI.

```http
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 Поскольку строковый параметр запроса обратного вызова имеет значение `JsonPCallback`, служба WCF возвращает ответ JSONP, показанный в следующем примере.

```json
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 Этот ответ JSONP содержит данные о клиенте в формате JSON, заключенные в имя функции обратного вызова, запрошенной веб-страницей. ScriptManager будет выполнять этот обратный вызов, используя тег скрипта для междоменного запроса, а затем передаст результат в обработчик onSuccess, который передан в операцию GetCustomer прокси ASP.NET AJAX.

 Пример состоит из двух веб-приложений ASP.NET: один содержит только службу WCF, а другой — веб-страницу. aspx, которая вызывает службу. При запуске решения Visual Studio 2012 будет размещать два веб-сайта на разных портах, что создает среду, в которой служба и клиент находятся в разных доменах.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1. Откройте решение для образца JSONP.  
  
2. Нажмите клавишу F5, чтобы запустить `http://localhost:26648/JSONPClientPage.aspx` в браузере.  
  
3. Обратите внимание, что после загрузки страницы входные текстовые значения "Name" и "Address" заполняются значениями.  Эти значения были предоставлены из вызова службы WCF после того, как браузер завершил отрисовку страницы.
