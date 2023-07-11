<h1>Release Schedule</h1>

<h2>Bug Fixes</h2>
<ol>
    <li>Bug fixes and minor improvements will be pushed every two weeks on Tuesday.</li>
    <li>What classifies as a bug/minor improvement? Anything that can be fixed without having to restructure classes/major functions in the code.</li>
    <li>Ideally, I'll get through every bug in my list, but sometimes, that just isn't possible. Those that are fixed will all be released all at once.</li>
</ol>

<h2>Feature Additions</h2>
<ol>
    <li>New Features will be released at the first Tuesday of every month, once finished, in addition to the bug fixes</li>
    <li>What constitutes a new feature? Anything that decently improve either quality of life, or gives extra functionality without having to restructure functions/classes. For the most part, these will be separate modules.</li>
</ol>

<h2>Major Releases</h2>
<ol>
    <li> This is the most flexible of the three for release schedule due to the massive size rollout. Early on, while I'm still understanding just how far I need to go, there will be one probably once every 3 months. Later on, That could shift out to a yearly basis. </li>
    <li> Major Releases are complete overhauls to the code for optimizational and structural reasons. I will do my best to keep function names the same to the end user, which should have those changing less and less as time goes on. As it stands, the only area where I see function names remotely changing are in regard to the yamlish parser.
</ol>
<h1></h1>
<h1>Git Workflow</h1>
<h2>Branch management</h2>
<p>While branch management isn't exactly new to me, there never needed to be true structure before this, so this is subject to change as more optimizations are found. I'll be taking heavy R&D from "https://nvie.com/posts/a-successful-git-branching-model/"</p>
<ol>
    <li>Classic git, every repository will have 3 branches, Master(Production), Development(For feature additions and bug fixing), and Major(for major code reconstruction and optimization)</li>
    <li>Bug fixes need to have individual branches that work off Development and will get merged into where appropriate.</li>
</ol>

<h2>Branch Merging Process</h2>
<p>This is the main portion this whole file is needed. Each merge for bug fixes, feature improvements, and master version updates will all have slightly different methods.</p>

<h3>Bug fixes</h3>
<ol>
    <li>List the bug in bugs file for fixing triage with reproduction notes</li>
    <li>Create a separate branch off development for the individual bug</li>
    <li>After thorough testing the bug is resolved, merge with commmit history into Development.</li>
    <li>Copy/paste the bug and primary key into bugs_resolved, documenting the solution, and patch resolved for.</li>
    <li>Delete the bug branch</li>
</ol>

<h3>Standard Development</h3>
<ol>
    <li>Each development branch will have a name corresponding to it's release.</li>
    <li>Each Additional feature on said development branch needs it's own branch, only merging in when prepping for release.</li>
    <li>Each first commit for a branch needs it's own feature_readme, listing the feature to be added, intended usage, and function/class dependencies</li>
    <li>Features can be considered completed when they have their own minimum viable product (per se), and have an updated future_readme.</li>
    <li>Once a feature update is being planned for release, each feature needs to be merged, with the commit history, into Development, one at a time. Once it has been tested and major bugs resolved, update the splash_page website, readme, and move on to the next feature. </li>  
</ol>

<h3>Major Releases</h3>
<p>There will come a point in time where overarching logic on a package level seems to be repeating itself, or pose more far-reaching compatibility if modified. The most obvious form of this is python 3.0's f-strings, or in this case, I can already see the yamlish parser going a lot farther with more than just flask in web development, if is more refined and has it's own package. This doesn't seem to fall into the standard development cycle well, and lowers dependability if it's changed frequently.
<ol>
    <li>When a Major Release is being scheduled, there needs to be a release_readme, a catalog of user-available functions (what's changed/added/remains), updated website examples of each feature, preferably showing the documentation of said feature in the website example </li>
    <li>Internally, all feature_readme's need to be pulled into one document for a few purposes</li>
    <ol>
        <li>Translate usage to production Readme.md</li>
        <li>See overarching logic where commonly reused sections would potentionally need their own module</li>
        <li>See which modules need to be optimized due to massive use (multi-processing/multi-threading candidates)</li>
    </ol>
    <li>Each Major implementation needs to follow this basic line</li>
    <ol>
    <li>Add the test file functions to the master check file for core utilities</li> 
    <li>Merge the extra features keeping commit history</li>
    <li>Run to check for bugs by checking outputs in script</li>
    <li>Once said bugs have been fixed, double-check the Readme's and update as appropriate</li>
    <li>Move on to next feature</li>
    </ol>
</ol>