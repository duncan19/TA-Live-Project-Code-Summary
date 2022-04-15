# CodeSummary_LiveProject
Tech Academy C# Live Project Code Summary
<h1>Introduction</h1>
For the last two weeks of my time at the Tech Academy, I worked on a team with multipule other students to help develop a new content management system(CMS) for a local theatre/acting company's website. This project was built with ASP .NET MVC and Entity Framework using C#. This interactive MVC web application allows the managing of content for users who are not well versed in tech, and want to easily manage what displays on their website. For this project we utilized an Agile work environment in Azure DevOps and SCRUM processes, which  involved daily standups and weekly code retrospectives during the two week sprint. 
<h3>Table of Contents</h3>
* Designing the Home page<br>
* Creating entity Model and CRUD pages<br>
* Styling CRUD Pages<br>
* Conclusion<br>
<h1>Designing the Home page</h1>
For this story, I was assigned the task of designing the Home page for the Vertigo Theatre web application. I utilized Bootstrap in order to have organized collumns for the Homepage and rows to display the information that was needed there as well as other HTML and CSS tools to fully create a functional home page.

```C# and HTML
<div>
    <img class="Home-Index--TheatreLogo" src="~/Content/images/TheatreLogo.png" #" alt="Theater logo" />
    @*<p class="text-xl-center">@Html.ActionLink("About Theatre Vertigo", "About", new { }, new { @class = "CMS-text-bigger" })</p> this is the about btn*@
    @*<p class="lead">ASP.NET is a free web framework for building great Web sites and Web applications using HTML, CSS and JavaScript.</p>*@
    @*<p><a href="https://asp.net" class="btn btn-primary btn-lg">Learn more &raquo;</a></p>*@
</div>
<div class="row">
    <div class="column left Home-Index--SpotlightColumn">
        <h1 class="Home-Index--SectionTitle">SPOTLIGHT</h1>
        <img class="Home-Index--SpotlightImgs" src="~/Content/images/DollsHouse.png" />
        <img class="Home-Index--SpotlightImgs" src="~/Content/images/Tempest.png" />
    </div>
    <div class="column right Home-Index--DonoSponsColumn">
        <div class="row Home-Index--DonoTitleRow">
            <h1  class="Home-Index--SectionTitle">DONATIONS</h1>
        </div>
        <div class="row Home-Index--DonoBtnRow">
            <button onclick="href='Dono-Page'" type="button" class="btn btn-lg Home-Index--SupBtn">Click To Support</button>
        </div>
        <div class="row Home-Index--SponsRow">
            <h1 class="Home-Index--SectionTitle">SPONSORS</h1>
        </div>
        <div class="row Home-Index--SponsRowImgs">
            <img class="Home-Index--SponsImgType1" src="~/Content/images/Sponsors/LogoRoundColor.png" />
            <img class="Home-Index--SponsImgType1" src="~/Content/images/Sponsors/Ninkasi-white-text.png" />
            <img class="Home-Index--SponsImgType1" src="~/Content/images/Sponsors/Ellyn-Bye-Logo.png" />
        </div>
        <div class="row Home-Index--SponsImgRowImgs2">
            <img class="Home-Index--SponsImgType2" src="~/Content/images/Sponsors/OCF-logo-in-white-with-tagline-lg.png" />
        </div>
        <div class="row Home-Index--SponsImgRowImgs3">
            <img class="Home-Index--SponsImgType1" src="~/Content/images/Sponsors/RACC.png" />
        </div>
    </div>
</div>
<div class="row Home-Index--LandRowTitle">
    <h1 class="Home-Index--SectionTitle">LAND ACKNOWLEDGEMENT</h1>
</div>
<div class="row">
    <div class="column left Home-Index--TextLand">
        <p>Theater Vertigo humbly acknowledges we live and work on unceded, traditional tribal lands of the Multnomah, Wasco, Clackamas, CHinook bands, Kathlament, Tualatin Kalapuya, Cowlitz, Mollala, Cascades, Oregon City Tumwater, Confederated Tribes of the Grand Ronde and other indigenous peoples.</p>
        <p><b>We are on stolen land.</b></p>
        <p>Theatre Vertigo has been and continues to examine our community relationships to ensure our collaborators, partners and sponsors support the our regions Indigenous Nations and communities.</p>
        <p>One of the ways Theatre Vertigo is working to act on our commitment to being of service to the lands that we now share is to build bridges between our arts community and local Nations.</p>
    </div>
    <div class="column right Home-Index--ImgLand">
        <a target="_blank" rel="noopener noreferrer" href="https://nayapdx.org/">
            <img id="Home-Index--LandPic"src="~/Content/images/NAYAFamilyCenter.jpg">
        </a>
        <p id="Home-Index--PhotoText">Click to visit the NAYA Family Center to learn more about supporting our local indigenous communities.</p>
    </div>
</div>

```




```CSS
 /* CSS color variables */
/*:root { /* Color palette for css */
/*--main-color: #DB1A11;  Red */
/*--main-color--light: #F04D44;*/ /* Red, a shade lighter */
/*--secondary-color: #D6972A;*/ /* Yellow gold */
/*--light-color: #FFFBFB;*/ /* White */
/*--dark-color: #000000;*/ /* Black */
/*--secondary-color--dark: #9D7C39;*/ /* Dark Gold */
/*}*/
.Home-Index--TheatreLogo {
    width: 500px;
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-top: 150px;
    width: 50%;
}
.Home-Index--SpotlightColumn {
    float: left;
    padding: 10px;
    margin-right: 5%;
    width: 60%;
}

.Home-Index--DonoSponsColumn {
    width: 30%;
    padding: 10px;
}
.Home-Index--TextLand {
    width: 50%
}
.Home-Index--ImgLand {
    width: 50%
}
.Home-Index--SpotlightImgs {
    width: 100%;
    margin-top: 20px;
}
.Home-Index--Section-Title {
    padding: 10px;
    color: var(--light-color);
    border-bottom: 1px solid var(--main-color--light);
    font-family: Oswald;
}
.Home-Index--SupBtn {
    margin-top: 100px;
    margin-left: 10%;
    margin-right: 10%;
    background-color: var(--main-color--light);
    border: none;
    color: var(--light-color);
    padding: 20px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
}
.Home-Index--DonoBtnRow {
    margin-bottom: 150px;
}
.Home-Index--SponsImgType1 {
    height: 65px;
    width: 65px;
    margin: 10px;
}
.Home-Index--SponsImgType2 {
    height: 65px;
    width: 235px;
    margin: 5px;
}
.Home-Index--TextLand {
    float: left;
    padding: 10px;
    margin-right: 5%;
    width: 60%;
}

.Home-Index--ImgLand {
    width: 30%;
    padding: 10px;
}
#Home-Index--LandPic {
    margin-left: 35px;
}
#Home-Index--PhotoText {
    text-align: center;
}
```







<h1>Creating entity Model and CRUD pages</h1>
For the this story I was assigned the task of creating an entity model of a Cast Member with defined properties and value types. I used a code first approach-- creating my model in code before creating the model. I was also tasked with implementing a Position enum for the Main Role property. I also commented out the Photo property with Byte[] array value type as it was going to be used in a different story. 




```C#
namespace TheatreCMS3.Areas.Prod.Models
{
    public class CastMember
    {
        public int CastMemberId { get; set; }
        public string Name { get; set; }
        public int YearJoined { get; set; }
        public PositionRole MainRole { get; set; }
        public string Bio { get; set; }
        
        //public Byte Photo { get; set; }
        public bool CurrentMember { get; set; }
        public string Character { get; set; }
        public int CastYearLeft { get; set; }
        public int DebutYearLeft { get; set; }
    }
    public enum PositionRole
    {
        Actor = 0,
        Director = 1,
        Technician = 2,
        StageManager = 3,
        Other = 4
    }
}
```
Scaffolding the CRUD pages via Controller
Here I used the power of Entity Framework to scaffold my Cast Member controller and create CRUD functionality.




```C#
namespace TheatreCMS3.Areas.Prod.Controllers
{
    public class CastMemberController : Controller
    {
        private ApplicationDbContext db = new ApplicationDbContext();

        // GET: Prod/CastMember
        public ActionResult Index()
        {
            return View(db.CastMembers.ToList());
        }

        // GET: Prod/CastMember/Details/5
        public ActionResult Details(int? id)
        {
            if (id == null)
            {
                return new HttpStatusCodeResult(HttpStatusCode.BadRequest);
            }
            CastMember castMember = db.CastMembers.Find(id);
            if (castMember == null)
            {
                return HttpNotFound();
            }
            return View(castMember);
        }

        // GET: Prod/CastMember/Create
        public ActionResult Create()
        {
            return View();
        }

        // POST: Prod/CastMember/Create
        // To protect from overposting attacks, enable the specific properties you want to bind to, for 
        // more details see https://go.microsoft.com/fwlink/?LinkId=317598.
        [HttpPost]
        [ValidateAntiForgeryToken]
        public ActionResult Create([Bind(Include = "CastMemberId,Name,YearJoined,MainRole,Bio,CurrentMember,Character,CastYearLeft,DebutYearLeft")] CastMember castMember)
        {
            if (ModelState.IsValid)
            {
                db.CastMembers.Add(castMember);
                db.SaveChanges();
                return RedirectToAction("Index");
            }

            return View(castMember);
        }

        // GET: Prod/CastMember/Edit/5
        public ActionResult Edit(int? id)
        {
            if (id == null)
            {
                return new HttpStatusCodeResult(HttpStatusCode.BadRequest);
            }
            CastMember castMember = db.CastMembers.Find(id);
            if (castMember == null)
            {
                return HttpNotFound();
            }
            return View(castMember);
        }

        // POST: Prod/CastMember/Edit/5
        // To protect from overposting attacks, enable the specific properties you want to bind to, for 
        // more details see https://go.microsoft.com/fwlink/?LinkId=317598.
        [HttpPost]
        [ValidateAntiForgeryToken]
        public ActionResult Edit([Bind(Include = "CastMemberId,Name,YearJoined,MainRole,Bio,CurrentMember,Character,CastYearLeft,DebutYearLeft")] CastMember castMember)
        {
            if (ModelState.IsValid)
            {
                db.Entry(castMember).State = EntityState.Modified;
                db.SaveChanges();
                return RedirectToAction("Index");
            }
            return View(castMember);
        }

        // GET: Prod/CastMember/Delete/5
        public ActionResult Delete(int? id)
        {
            if (id == null)
            {
                return new HttpStatusCodeResult(HttpStatusCode.BadRequest);
            }
            CastMember castMember = db.CastMembers.Find(id);
            if (castMember == null)
            {
                return HttpNotFound();
            }
            return View(castMember);
        }

        // POST: Prod/CastMember/Delete/5
        [HttpPost, ActionName("Delete")]
        [ValidateAntiForgeryToken]
        public ActionResult DeleteConfirmed(int id)
        {
            CastMember castMember = db.CastMembers.Find(id);
            db.CastMembers.Remove(castMember);
            db.SaveChanges();
            return RedirectToAction("Index");
        }

        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                db.Dispose();
            }
            base.Dispose(disposing);
        }
    }
}
```


<h1>Styling Crud Pages</h1>
I was assigned the task of styling the recently created CRUD pages for the Cast Member model. 



```C#
@model TheatreCMS3.Areas.Prod.Models.CastMember

@{
    ViewBag.Title = "Create";
    Layout = "~/Views/Shared/_Layout.cshtml";
}



@using (Html.BeginForm())
{
    @Html.AntiForgeryToken()

<div class="form-horizontal">
    <div class="Cast-Create--Center">
        <h1>Create CastMember</h1>
    </div>
    <div class="Cast-Create--Background">

        @Html.ValidationSummary(true, "", new { @class = "text-danger" })
        <div class="form-group">
            @Html.LabelFor(model => model.Name, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Name, new { htmlAttributes = new { @class = "form-control Cast-Create--FormBorder", @placeholder = "Enter Name" } })
                @Html.ValidationMessageFor(model => model.Name, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.YearJoined, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.YearJoined, new { htmlAttributes = new { @class = "form-control Cast-Create--FormBorder", @placeholder = "Year Joined" } })
                @Html.ValidationMessageFor(model => model.YearJoined, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.MainRole, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EnumDropDownListFor(model => model.MainRole, htmlAttributes: new { @class = "form-control Cast-Create--FormBorder" })
                @Html.ValidationMessageFor(model => model.MainRole, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Bio, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Bio, new { htmlAttributes = new { @class = "form-control Cast-Create--FormBorder", @placeholder = "Bio" } })
                @Html.ValidationMessageFor(model => model.Bio, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.CurrentMember, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                <div class="checkbox">
                    @Html.EditorFor(model => model.CurrentMember)
                    @Html.ValidationMessageFor(model => model.CurrentMember, "", new { @class = " Cast-Create--FormBorder text-danger" })
                </div>
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.Character, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.Character, new { htmlAttributes = new { @class = "form-control Cast-Create--FormBorder", @placeholder = "Character" } })
                @Html.ValidationMessageFor(model => model.Character, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.CastYearLeft, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.CastYearLeft, new { htmlAttributes = new { @class = "form-control Cast-Create--FormBorder", @placeholder = "Cast Years Left" } })
                @Html.ValidationMessageFor(model => model.CastYearLeft, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            @Html.LabelFor(model => model.DebutYearLeft, htmlAttributes: new { @class = "control-label col-md-2" })
            <div class="col-md-10">
                @Html.EditorFor(model => model.DebutYearLeft, new { htmlAttributes = new { @class = "form-control Cast-Create--FormBorder", @placeholder = "Debut Years Left" } })
                @Html.ValidationMessageFor(model => model.DebutYearLeft, "", new { @class = "text-danger" })
            </div>
        </div>

        <div class="form-group">
            <div class="">
                <input type="submit" value="Create" class="Cast-Create--button1" />
            </div>
        </div>
        <div>
            @Html.ActionLink("Back to List", "Index", "CastMember", null, new { @class = "Cast-Create--button2" })
        </div>
    </div>
</div>
}



@section Scripts {
    @Scripts.Render("~/bundles/jqueryval")
}
```



```C#

.Cast-Create--Center {
    text-align: center;
}
.Cast-Create--Background {
    background-color: var(--secondary-color--dark);
    margin: auto;
    width: 600px;
}
.Cast-Create--FormBorder:focus {
    border: 2px solid var(--main-color--light);
}
.Cast-Create--button1 {
    background-color: var(--main-color--light); /* Red, a shade lighter */
    border: none;
    color: var(--dark-color);
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    width: 100%;
    border-radius: 0.25rem;
}

.Cast-Create--button2 {
    background-color: var(--main-color); /* Red*/
    border: none;
    color: var(--dark-color);
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    width: 100%;
    border-radius: 0.25rem;
}
.Cast-Create--button1:hover {
    background-color: var(--main-color); /* Red */
    color: var(--dark-color);
}

.Cast-Create--button2:hover {
    background-color: var(--main-color); /* Red */
    color: var(--dark-color);
}
```


<h1>Conclusion</h1>
This live project was a great opportunity for me to learn how to put what I learned into practice. I was able to learn the positives of what it is like to work along side someone else as well as the challenges that it brought with it as well. I also was able to learn about the Agile and SCRUM team managment and get a good feel on how to work using a Project Managment System like Azure Dev Ops. Overall I enjoyed the live project experiance a lot and I am looking forward to having similar experiences later on in my career.
