## <a name="register-the-database-context"></a><span data-ttu-id="c82bc-101">Veritabanı bağlamı kaydetme</span><span class="sxs-lookup"><span data-stu-id="c82bc-101">Register the database context</span></span>

<span data-ttu-id="c82bc-102">Veritabanı bağlamı denetleyicisi olarak eklenmeye için ile kaydetmek ihtiyacımız [bağımlılık ekleme](xref:fundamentals/dependency-injection) kapsayıcı.</span><span class="sxs-lookup"><span data-stu-id="c82bc-102">In order to inject the database context into the controller, we need to register it with the [dependency injection](xref:fundamentals/dependency-injection) container.</span></span> <span data-ttu-id="c82bc-103">Veritabanı bağlamı için yerleşik destek kullanarak hizmet kapsayıcısı kaydetme [bağımlılık ekleme](xref:fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="c82bc-103">Register the database context with the service container using the built-in support for [dependency injection](xref:fundamentals/dependency-injection).</span></span> <span data-ttu-id="c82bc-104">Değiştir *haline* aşağıdaki dosyasıyla:</span><span class="sxs-lookup"><span data-stu-id="c82bc-104">Replace the contents of the *Startup.cs* file with the following:</span></span>

<span data-ttu-id="c82bc-105">[!code-csharp[Ana](../../tutorials/first-web-api/sample/TodoApi/Startup.cs?highlight=2,4,12)]</span><span class="sxs-lookup"><span data-stu-id="c82bc-105">[!code-csharp[Main](../../tutorials/first-web-api/sample/TodoApi/Startup.cs?highlight=2,4,12)]</span></span>

<span data-ttu-id="c82bc-106">Önceki kod:</span><span class="sxs-lookup"><span data-stu-id="c82bc-106">The preceding code:</span></span>

* <span data-ttu-id="c82bc-107">Biz değil kullanmakta olduğunuz kodunu kaldırır.</span><span class="sxs-lookup"><span data-stu-id="c82bc-107">Removes the code we're not using.</span></span>
* <span data-ttu-id="c82bc-108">Hizmet kapsayıcıya bir bellek içi veritabanına eklenen belirtir.</span><span class="sxs-lookup"><span data-stu-id="c82bc-108">Specifies an in-memory database is injected into the service container.</span></span>