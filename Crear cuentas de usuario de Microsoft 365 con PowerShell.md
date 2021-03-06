<h1 id="use-the-azure-active-directory-powershell-for-graph-module"><span data-ttu-id="77978-143">Crear cuentas de usuario de Microsoft 365 con PowerShell - Microsoft 365 Enterprise</span></h1>				
							
							
<p><span data-ttu-id="77978-105">Puede usar PowerShell para Microsoft 365 para crear cuentas de usuario de forma eficaz, incluidas varias cuentas.</span><span class="sxs-lookup"><span data-stu-id="77978-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span></p>
<p><span data-ttu-id="77978-106">Al crear cuentas de usuario en PowerShell, siempre se requieren determinadas propiedades de cuenta.</span><span class="sxs-lookup"><span data-stu-id="77978-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="77978-107">Otras propiedades no son necesarias, pero son importantes.</span><span class="sxs-lookup"><span data-stu-id="77978-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="77978-108">Vea la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="77978-108">See the following table.</span></span></p>
<table>
<thead>
<tr>
<th style="text-align: left;"><span data-ttu-id="77978-109"><strong>Nombre de propiedad</strong></span><span class="sxs-lookup"><span data-stu-id="77978-109"><strong>Property name</strong></span></span></th>
<th style="text-align: left;"><span data-ttu-id="77978-110"><strong>Obligatorio</strong></span><span class="sxs-lookup"><span data-stu-id="77978-110"><strong>Required?</strong></span></span></th>
<th style="text-align: left;"><span data-ttu-id="77978-111"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="77978-111"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align: left;"><span data-ttu-id="77978-112"><strong>DisplayName</strong></span><span class="sxs-lookup"><span data-stu-id="77978-112"><strong>DisplayName</strong></span></span> <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-113">Sí</span><span class="sxs-lookup"><span data-stu-id="77978-113">Yes</span></span>  <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-114">Este es el nombre para mostrar que se usa en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="77978-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="77978-115">Por ejemplo, <em>Caleb Sills</em>.</span><span class="sxs-lookup"><span data-stu-id="77978-115">For example, <em>Caleb Sills</em>.</span></span> <br></td>
</tr>
<tr>
<td style="text-align: left;"><span data-ttu-id="77978-116"><strong>UserPrincipalName</strong></span><span class="sxs-lookup"><span data-stu-id="77978-116"><strong>UserPrincipalName</strong></span></span> <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-117">Sí</span><span class="sxs-lookup"><span data-stu-id="77978-117">Yes</span></span>  <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-118">Este es el nombre de cuenta que se usa para iniciar sesión en los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="77978-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="77978-119">Por ejemplo, <em>CalebS @ contoso.onmicrosoft.com</em>.</span><span class="sxs-lookup"><span data-stu-id="77978-119">For example, <em>CalebS@contoso.onmicrosoft.com</em>.</span></span>  <br></td>
</tr>
<tr>
<td style="text-align: left;"><span data-ttu-id="77978-120"><strong>FirstName</strong></span><span class="sxs-lookup"><span data-stu-id="77978-120"><strong>FirstName</strong></span></span> <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-121">No</span><span class="sxs-lookup"><span data-stu-id="77978-121">No</span></span>  <br></td>
<td style="text-align: left;"></td>
</tr>
<tr>
<td style="text-align: left;"><span data-ttu-id="77978-122"><strong>Apellidos</strong></span><span class="sxs-lookup"><span data-stu-id="77978-122"><strong>LastName</strong></span></span> <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-123">No</span><span class="sxs-lookup"><span data-stu-id="77978-123">No</span></span>  <br></td>
<td style="text-align: left;"></td>
</tr>
<tr>
<td style="text-align: left;"><span data-ttu-id="77978-124"><strong>LicenseAssignment</strong></span><span class="sxs-lookup"><span data-stu-id="77978-124"><strong>LicenseAssignment</strong></span></span> <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-125">No</span><span class="sxs-lookup"><span data-stu-id="77978-125">No</span></span>  <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-126">Este es el plan de licencias (también conocido como plan de licencia o SKU) desde el que se asigna una licencia disponible a la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="77978-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="77978-127">La licencia define los servicios de Microsoft 365 que están disponibles para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="77978-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="77978-128">No es necesario asignar una licencia a un usuario al crear la cuenta, pero la cuenta debe tener una licencia para tener acceso a los servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="77978-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="77978-129">Dispone de 30 días para conceder una licencia a la cuenta de usuario después de crearla.</span><span class="sxs-lookup"><span data-stu-id="77978-129">You have 30 days to license the user account after you create it.</span></span></td>
</tr>
<tr>
<td style="text-align: left;"><span data-ttu-id="77978-130"><strong>Password</strong></span><span class="sxs-lookup"><span data-stu-id="77978-130"><strong>Password</strong></span></span> <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-131">No</span><span class="sxs-lookup"><span data-stu-id="77978-131">No</span></span>  <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-132">Si no especifica una contraseña, se asignará una contraseña aleatoria a la cuenta de usuario y la contraseña será visible en los resultados del comando.</span><span class="sxs-lookup"><span data-stu-id="77978-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="77978-133">Si especifica una contraseña, debe tener entre 8 y 16 caracteres de texto ASCII de los siguientes tipos: minúsculas, letras mayúsculas, números y símbolos.</span><span class="sxs-lookup"><span data-stu-id="77978-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br></td>
</tr>
<tr>
<td style="text-align: left;"><span data-ttu-id="77978-134"><strong>UsageLocation</strong></span><span class="sxs-lookup"><span data-stu-id="77978-134"><strong>UsageLocation</strong></span></span> <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-135">No</span><span class="sxs-lookup"><span data-stu-id="77978-135">No</span></span>  <br></td>
<td style="text-align: left;"><span data-ttu-id="77978-136">Se trata de un código de país válido ISO 3166-1 alpha-2.</span><span class="sxs-lookup"><span data-stu-id="77978-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="77978-137">Por ejemplo, <em>EE.</em> UU. para Estados Unidos y <em>FR</em> para Francia.</span><span class="sxs-lookup"><span data-stu-id="77978-137">For example, <em>US</em> for the United States, and <em>FR</em> for France.</span></span> <span data-ttu-id="77978-138">Es importante proporcionar este valor, ya que algunos servicios de Microsoft 365 no están disponibles en determinados países.</span><span class="sxs-lookup"><span data-stu-id="77978-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="77978-139">No puede asignar una licencia a una cuenta de usuario a menos que la cuenta tenga configurado este valor.</span><span class="sxs-lookup"><span data-stu-id="77978-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="77978-140">Para obtener más información, consulte <a href="https://go.microsoft.com/fwlink/p/?LinkId=691730" data-linktype="external">Sobre las restricciones de licencia</a>.</span><span class="sxs-lookup"><span data-stu-id="77978-140">For more information, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=691730" data-linktype="external">About license restrictions</a>.</span></span><br></td>
</tr>
</tbody>
</table>
<div class="NOTE">
<p><b>Nota</b></p>
<p><span data-ttu-id="77978-141"><a href="../admin/add-users/add-users?view=o365-worldwide" data-linktype="relative-path">Obtenga información sobre cómo crear cuentas de usuario</a> mediante el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="77978-141"><a href="../admin/add-users/add-users?view=o365-worldwide" data-linktype="relative-path">Learn how to create user accounts</a> by using the Microsoft 365 admin center.</span></span></p>
<p><span data-ttu-id="77978-142">Para obtener una lista de recursos adicionales, vea <a href="../admin/add-users/?view=o365-worldwide" data-linktype="relative-path">Administrar usuarios y grupos.</a></span><span class="sxs-lookup"><span data-stu-id="77978-142">For a list of additional resources, see <a href="../admin/add-users/?view=o365-worldwide" data-linktype="relative-path">Manage users and groups</a>.</span></span></p>
</div>
<h2 id="use-the-azure-active-directory-powershell-for-graph-module"><span data-ttu-id="77978-143">Use el módulo de PowerShell Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="77978-143">Use the Azure Active Directory PowerShell for Graph module</span></span></h2>
<p><span data-ttu-id="77978-144">En primer <a href="connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module" data-linktype="relative-path">lugar, conéctese a su inquilino de Microsoft 365</a>.</span><span class="sxs-lookup"><span data-stu-id="77978-144">First, <a href="connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-azure-active-directory-powershell-for-graph-module" data-linktype="relative-path">connect to your Microsoft 365 tenant</a>.</span></span></p>
<p><span data-ttu-id="77978-145">Después de conectarse, use la siguiente sintaxis para crear una cuenta individual:</span><span class="sxs-lookup"><span data-stu-id="77978-145">After you connect, use the following syntax to create an individual account:</span></span></p>
<pre><code class="lang-powershell">$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=&quot;&lt;user account password&gt;&quot;
New-AzureADUser -DisplayName &quot;&lt;display name&gt;&quot; -GivenName &quot;&lt;first name&gt;&quot; -SurName &quot;&lt;last name&gt;&quot; -UserPrincipalName &lt;sign-in name&gt; -UsageLocation &lt;ISO 3166-1 alpha-2 country code&gt; -MailNickName &lt;mailbox name&gt; -PasswordProfile $PasswordProfile -AccountEnabled $true
</code></pre>
<p><span data-ttu-id="77978-146">En este ejemplo se crea una cuenta para el usuario estadounidense <em>Caleb Sills</em>:</span><span class="sxs-lookup"><span data-stu-id="77978-146">This example creates an account for the US user <em>Caleb Sills</em>:</span></span></p>
<pre><code class="lang-powershell">$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=&quot;3Rv0y1q39/chsy&quot;
New-AzureADUser -DisplayName &quot;Caleb Sills&quot; -GivenName &quot;Caleb&quot; -SurName &quot;Sills&quot; -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
</code></pre>
<h2 id="use-the-microsoft-azure-active-directory-module-for-windows-powershell"><span data-ttu-id="77978-147">Use el Módulo Microsoft Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77978-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span></h2>
<p><span data-ttu-id="77978-148">En primer <a href="connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell" data-linktype="relative-path">lugar, conéctese a su inquilino de Microsoft 365</a>.</span><span class="sxs-lookup"><span data-stu-id="77978-148">First, <a href="connect-to-microsoft-365-powershell?view=o365-worldwide#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell" data-linktype="relative-path">connect to your Microsoft 365 tenant</a>.</span></span></p>
<h3 id="create-an-individual-user-account"><span data-ttu-id="77978-149">Cree una cuenta de usuario individual</span><span class="sxs-lookup"><span data-stu-id="77978-149">Create an individual user account</span></span></h3>
<p><span data-ttu-id="77978-150">Para crear una cuenta individual, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="77978-150">To create an individual account, use the following syntax:</span></span></p>
<pre><code class="lang-powershell">New-MsolUser -DisplayName &lt;display name&gt; -FirstName &lt;first name&gt; -LastName &lt;last name&gt; -UserPrincipalName &lt;sign-in name&gt; -UsageLocation &lt;ISO 3166-1 alpha-2 country code&gt; -LicenseAssignment &lt;licensing plan name&gt; [-Password &lt;Password&gt;]
</code></pre>
<div class="NOTE">
<p><b>Nota</b></p>
<p><span data-ttu-id="77978-151">PowerShell Core no admite el módulo de Microsoft Azure Active Directory para Windows PowerShell módulo y cmdlets que tienen <em>Msol</em> en su nombre.</span><span class="sxs-lookup"><span data-stu-id="77978-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have <em>Msol</em> in their name.</span></span> <span data-ttu-id="77978-152">Ejecute estos cmdlets desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77978-152">Run these cmdlets from Windows PowerShell.</span></span></p>
</div>
<p><span data-ttu-id="77978-153">Para obtener una lista de los nombres de planes de licencias disponibles, use este comando:</span><span class="sxs-lookup"><span data-stu-id="77978-153">To list the available licensing plan names, use this command:</span></span></p>
<pre><code class="lang-powershell">Get-MsolAccountSku
</code></pre>
<p><span data-ttu-id="77978-154">En este ejemplo se crea una cuenta para el usuario estadounidense <em>Caleb Sills</em> y se asigna una licencia del plan de licencias <code>contoso:ENTERPRISEPACK</code> (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="77978-154">This example creates an account for the US user <em>Caleb Sills</em>, and assigns a license from the <code>contoso:ENTERPRISEPACK</code> (Office 365 Enterprise E3) licensing plan.</span></span></p>
<pre><code class="lang-powershell">New-MsolUser -DisplayName &quot;Caleb Sills&quot; -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
</code></pre>
<h3 id="create-multiple-user-accounts"><span data-ttu-id="77978-155">Crear varias cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="77978-155">Create multiple user accounts</span></span></h3>
<ol>
<li><p><span data-ttu-id="77978-p108">Cree un archivo de valores separados por comas (CSV) que contenga la información necesaria de la cuenta de usuario. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="77978-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span></p>
<pre><code class="lang-powershell">UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
</code></pre>
<div class="NOTE">
<p><b>Nota</b></p>
<p><span data-ttu-id="77978-158">Los nombres de columna y su orden en la primera fila del archivo CSV son arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="77978-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="77978-159">Pero asegúrese de que el orden de los datos en el resto del archivo coincide con el orden de los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="77978-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="77978-160">Y use los nombres de columna para los valores de parámetro en el comando de PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="77978-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span></p>
</div>
</li>
<li><p><span data-ttu-id="77978-161">Utilice la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="77978-161">Use the following syntax:</span></span></p>
<pre><code class="lang-powershell"> Import-Csv -Path &lt;Input CSV File Path and Name&gt; | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path &lt;Output CSV File Path and Name&gt;
</code></pre>
<p><span data-ttu-id="77978-162">En este ejemplo se crean cuentas de usuario desde el archivo <em>C:\My Documents\NewAccounts.csv</em> y se registra el resultado en un archivo denominado <em>C:\My Documents\NewAccountResults.csv</em>.</span><span class="sxs-lookup"><span data-stu-id="77978-162">This example creates user accounts from the file <em>C:\My Documents\NewAccounts.csv</em> and logs the results in a file named <em>C:\My Documents\NewAccountResults.csv</em>.</span></span></p>
<pre><code class="lang-powershell">Import-Csv -Path &quot;C:\My Documents\NewAccounts.csv&quot; | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path &quot;C:\My Documents\NewAccountResults.csv&quot;
</code></pre>
</li>
<li><p><span data-ttu-id="77978-163">Revise el archivo de salida para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="77978-163">Review the output file to see the results.</span></span> <span data-ttu-id="77978-164">No especificamos contraseñas, por lo que las contraseñas aleatorias generadas por Microsoft 365 son visibles en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="77978-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span></p>
</li>
</ol>
