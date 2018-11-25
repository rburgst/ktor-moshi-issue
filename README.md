## Sample repo showing a problem with ktor-moshi

see https://github.com/rharter/ktor-moshi/issues/3

1. launch the app in IntelliJ
2. send an http request to http://localhost:8080/json/gson 
   (see also `./requests.http`)

### Expected

a JSON response

### Actual

```
2018-11-25 14:22:11.172 [nettyCallPool-4-1] ERROR Application - Unhandled: GET - /json/gson
java.lang.AbstractMethodError: com.ryanharter.ktor.moshi.MoshiConverter.convertForSend(Lio/ktor/util/pipeline/PipelineContext;Lio/ktor/http/ContentType;Ljava/lang/Object;Lkotlin/coroutines/Continuation;)Ljava/lang/Object;
	at io.ktor.features.ContentNegotiation$Feature$install$2.invokeSuspend(ContentNegotiation.kt:82)
	at io.ktor.features.ContentNegotiation$Feature$install$2.invoke(ContentNegotiation.kt)
	at io.ktor.util.pipeline.SuspendFunctionGun.loop(PipelineContext.kt:248)
	at io.ktor.util.pipeline.SuspendFunctionGun.access$loop(PipelineContext.kt:63)
	at io.ktor.util.pipeline.SuspendFunctionGun.proceed(PipelineContext.kt:111)
	at io.ktor.util.pipeline.SuspendFunctionGun.execute(PipelineContext.kt:131)
	at io.ktor.util.pipeline.Pipeline.execute(Pipeline.kt:24)
	at com.example.ApplicationKt$module$2$2.invokeSuspend(Application.kt:42)
	at com.example.ApplicationKt$module$2$2.invoke(Application.kt)
	at io.ktor.util.pipeline.SuspendFunctionGun.loop(PipelineContext.kt:248)
	at io.ktor.util.pipeline.SuspendFunctionGun.access$loop(PipelineContext.kt:63)
```
