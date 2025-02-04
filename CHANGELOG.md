1.15
----
 * Fix error handling when merging pull requests
 * StashApiClient: Refactor and simplify HTTP response processing
 * StashRepository: Improve logging when a job is queued
 * StashBuildListener: Make logging in onStarted() more informative
 * StashCause: Generate environment on demand, don't keep it
 * Use assertThrows from JUnit 4.13 instead of ExpectedException
 * StashRepository: Reduce nesting in isForTargetBranch()
 * StashRepository: Log triggering decisions to the poll log only
 * StashRepository: Log exceptions to the poll log and to the system log
 * StashRepository: Take pollLog as a constructor argument
 * StashPullRequestCommentTest: Don't check that compareTo(null) throws
 * StashPullRequestResponseValueRepositoryRepository: Remove useless null check
 * StashApiClient: Use Iterable instead of List as argument when possible
 * StashRepository: Add Nullable annotations to functions that can return null
 * StashApiClient: Remove unnecessary variables when returning a value
 * StashApiClientTest: Fix tests on systems that listen to HTTP port 8080
 * StashRepository: Only cancel queue items for the same job
 * Use StringUtils.isEmpty() and StringUtils.isNotEmpty() where appropriate

1.14
----
 * [JENKINS-59833] Prevent unwanted folding of multiple queue tasks into one
 * pom.xml: Use GitHub for plugin's documentation on plugins.jenkins.io
 * Use job.getFullName() in logs, it's unique for every Item in Jenkins
 * StashBuildTrigger: Don't throw NullPointerException unnecessarily
 * Construct StashApiClient in StashBuildTrigger

1.13
----
 * StashBuildTrigger: Fix exception if run() is called after stop()
 * StashPostBuildCommentAction: Remove, it has been obsolete since version 1.9
 * Remove template parameters that can be deduced
 * pom.xml: Update fmt-maven-plugin to version 2.9
 * Update Wiremock to version 2.24.0
 * StashRepositoryTest: Use Collections.singletonList for a single element list
 * Update to parent POM 3.48, add SpotBugs settings
 * Add a "Polling Log" page as a link on the project page
 * StashPullRequestActivity: Don't implement Comparable, it is not used
 * StashRepository: Use StringUtils.containsIgnoreCase() and StringUtils.isEmpty()
 * Remove repackaged EasySSLProtocolSocketFactory, it's not used anymore
 * Update to Apache httpclient 4.5.x
 * StashPullRequestResponseValueRepositoryBranch: Use lowercase "name" field
 * StashApiClientTest: Add a test for parsing all pull request fields
 * StashPullRequestComment: Use a method reference instead of a lambda

1.12
----
 * Fix Jenkins not detecting bad pom.xml formatting
 * Merge StashPullRequestsBuilder into StashRepository
 * Update to Jackson2 API, use Jenkins Jackson2 API plugin
 * Use Apache HttpComponents Client 4.x API Plugin
 * Require Jenkins 2.60.3 instead of 2.60.1

1.11
-----
 * StashPullRequestComment: Rewrite Comparable interface implementation
 * Enable optional support for Jenkins pipelines
 * Depend on hamcrest, not on hamcrest-library
 * StashBuildTrigger: Make field defaults match config.jelly
 * StashBuildTrigger: Use @DataBoundSetter for advanced settings
 * StashBuildTrigger: Rename StashBuildTriggerDescriptor to DescriptorImpl
 * Clean up exception handling in StashApiClient
 * StashApiClientTest: Add WireMock based tests for StashApiClient
 * StashRepositoryTest: No need to stub getCiSkipPhrases() everywhere
 * StashBuildTrigger: Remove all references to projectPath, it's not used
 * StashBuildListener: Log error updating build description to the build output
 * StashBuildTrigger: Use correct getter names for config.jelly fields
 * StashPullRequestsBuilder: Fix compile error, "project" should be "job" now
 * StashBuildListenerTest: Add test for onCompleted() with matching cause
 * Replace AbstractProject and AbstractBuild with Job and Run (#107)
 * StashRepository: Merge init() into the constructor
 * StashRepository: Log stack trace when catching StashApiException
 * Make project and repository name available everywhere in project configuration
 * Use snake_case for unit test names
 * Use allOf() matcher to check maps
 * Use contains() matcher to check lists
 * Move public members above private members
 * Expand wildcard imports
 * Fill parameter values from environment variables added by the plugin
 * Add @Nonnull annotations, remove unnecessary null checks
 * Fix handling of failures to fetch the PR list and the PR comments
 * StashRepository: Implement in terms of Job, not AbstractProject
 * Merge StashBuilds into StashBuildListener


1.10
-----
 * findbugs-exclude.xml: Remove suppressions for StashBuildTrigger
 * StashPostBuildComment: Don't override newInstance(), it's not needed
 * Fix FindBugs warnings about StashBuildTrigger#job being null
 * StashPostBuildComment: Remove redundant "implements"
 * StashRepository: Use Java style array declaration
 * StashBuildTriggerTest: Use varargs for parameter definitions
 * StashApiClient: Remove all special treatment for UnsupportedEncodingException
 * StashApiClient: Rename all variables for HTTP requests to "request"
 * StashApiClient: Provide better descriptions for all timeouts
 * StashApiClient: Remove useless casts and class prefixes
 * StashApiClient: Annotate functions as @Nullable if they can return null
 * StashRepository: Clean up comment sorting, add comments
 * StashBuildEnvironmentContributor: Pass environment variables to pipelines (#96)
 * Don't accept any new parameter names from pull request comments
 * StashRepositoryTest: Don't mock pullRequest, repository and repoRepo
 * StashRepositoryTest: Refactor creation of a pull request list
 * StashRepositoryTest: Replace "CLOSED" with "MERGED"
 * StashRepositoryTest: Remove verifications
 * Increase socket timeout to 30s (#52)

1.9
-----

* StashBuildListener: Get the trigger using ParameterizedJobMixIn.getTrigger()
* StashRepository: Use StringUtils.isNotEmpty(), it treats null as empty
* StashRepositoryTest: Add unit tests for isForTargetBranch() and isSkipBuild()
* StashRepositoryTest: Set Mockito strictness to STRICT_STUBS
* StashRepository: Make string constants private, other classes don't use them
* Annotate compareTo() methods with @Override
* Fix credential matching by Stash URL
* StashRepository: Only consider pull requests in the "OPEN" state
* StashRepository: Change constructor to get needed objects directly
* pom.xml: Replace unneeded dependency on git with direct dependencies
* StashBuildTrigger: Use isBuildable() instead of isDisabled()
* StashBuildTrigger: Call super.start() first
* Fix canceling outdated Maven projects
* Use Hamcrest in unit tests, it gives better diagnostics
* Iterate over map entries more efficiently
* StashRepository: Don't take projectPath in constructor, it's unused
* Fix warnings about raw types
* Fix spelling of "mergeable"
* Fix spelling of "comment"
* StashRepository: Unbox the result of isPullRequestMergable()
* [JENKINS-41771] StashPostBuildComment: disable serialization
* StashBuildTrigger: Hide Stash PR build trigger from pipelines for now
* Rename StashAditionalParameterEnvironmentContributor
* Update the lowest supported Jenkins version to 2.60.1
* Remove StashBuilds#getCause(), call build.getCause() directly
* Use logger names automatically derived from the containing class names
* StashBuilds: Use the trigger member when merging the PR
* style: always use "if" with braces, remove empty comments
* [JENKINS-56349] Protect StashBuildTrigger#run() against crash if called early
* [JENKINS-56349] Make StashPullRequestsBuilder constructor take two arguments
* Skip default parameters that are null
* StashBuildTrigger: Respect the quiet period set for the job
* Fix post build comments for matrix builds
* style: reformat code to match google formatter
* chore: enable fmt-maven-plugin
* StashApiClient: Return Collections.emptyList(), not Collections.EMPTY_LIST
* Avoid wildcard import
* Remove trailing space, expand tabs, add final newlines
* Provide environment variables to downstream builds
* Don't put environment variables to the build parameters
* Add help files for all fields (#42)


v1.8
-----

    Bug fix - post correct links to Jenkins in Stash comments with recent Jenkins versions
    Added ability to probe Stash for the merge status to make Stash update the refspecs
    Using repackaged EasySSLProtocolSocketFactory from commons-httpclient
    Improved field names in the configuration
    Improved README.md

v1.7.1
-----

    Check the PR conflict state even if the PR is mergeable
    Change the default to check the conflict state
    Added documentation about merging and race conditions

v1.7.0
-----

    Bug fix - the only build on comment mode does not work after the first comment
    Added ability to merge on build success
    Added ability to cancel previously queued and running jobs when the PR is updated
    Using EnvironmentContributor for variables
    Only offer valid credentials in the credentials drop down

v1.6.0
-----

    Bug fix - Jenkins issue #30558 - sockets causing problems with hanging triggers
    Bug fix - include default parameter values in build queue
    Added project name to log messages

v1.5.3
-----

    Branch name filters can now be regular expressions
    Support all build states (now all states are reported, not just success or everything else as failure in the build PR comment)

v1.5.2
-----

    Fix PR branch filters

v1.5.1
-----

    Added ability to only keep the most recent PR status comment
    Logging improvements
    Ability to limit PR builds to specified target branches only

v1.5.0
-----

    Added credentials support - this is a breaking change, please add a username/password credential for the user you want PR build comments to be posted from. Old builds will fail until you update them with the right credentials from the credentials plugin. 
    Fixup branch & ref specs in git config - again this is a breaking change and you should update your git configuration (URL, ref spec & branch specifier), please see the updated README  

v1.4.2
-----

    Fix bug with Stash response code handling 

v1.4.1
-----

    Better error handling when Stash returns 200/OK response
    Added support for custom parameters in the 'test this please' comment
    Option to ignore SSL certificates (useful if you dont have proper certificates with your Stash instance)
    Fixes for PR pagination

v1.4.0
-----

    Added build duration to build finished message in PR - useful for tracking runtimes/test overheads added in PRs. 
    Improved Stash polling
    Better JSON handling 
    Added better support for the notify Stash plugin to only tag the source commit SHA1
    Bugfixes

v1.3.1
-----

    Use Git SCM as provider for hostname and credentials needed for the pull request builder
    Now it is also possible to verify pull requests from another fork (while previously it would only work in the same repository, or at least with the merge before build feature). Prerequisite is that you add +refs/pull-requests/:refs/remotes/origin/pr/ as refspec.
    Additionally you can filter on the target branch which makes you able to restrict checking pull requests on a specific (release) branch.
    Support for global environment variables has been added.

v1.2.0
-----

    Added post build custom comment support
    Marked credentials plugin as required dependency for upcoming v1.3.0 release with Credentials support

v1.1.0
-----

    Added ability to customise the build phrase (change from the default of 'test this please')
    Added ability to only have PR built if its merge-able (i..e has been approved)
    Added ability to only have PR built if its not conflicted
    Added check to only build PR on comment (don't auto build) based on build phrase (default is 'test this please')

v1.0.1
-----

    Fix bug with passing branch names with a '/'
    Reduce logging verbosity

v1.0.0
-----

    Initial release
