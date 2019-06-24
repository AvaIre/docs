# Contribution Guide

- [Bug Reports](#bug-reports)
- [Which Branch?](#which-branch)
- [Coding Style](#coding-style)
    - [ESDoc](#esdoc)

<a name="bug-reports"></a>
## Bug Reports

To encourage active collaboration, AvaIre strongly encourages pull requests, not just bug reports. "Bug reports" may also be sent in the form of a pull request containing a failing test.

However, if you file a bug report, your issue should contain a title and a clear description of the issue. You should also include as much relevant information as possible and a code sample that demonstrates the issue. The goal of a bug report is to make it easy for yourself - and others - to replicate the bug and develop a fix.

Remember, bug reports are created in the hope that others with the same problem will be able to collaborate with you on solving it. Do not expect that the bug report will automatically see any activity or that others will jump to fix it. Creating a bug report serves to help yourself and others start on the path of fixing the problem.

<a name="which-branch"></a>
## Which Branch?

**All** bug fixes should be sent to the latest stable branch or to the current LTS branch (0.X). Bug fixes should never be sent to the master branch unless they fix features that exist only in the upcoming release.

**Minor** features that are fully backward compatible with the current AvaIre release may be sent to the latest stable branch.

**Major** new features should always be sent to the master branch, which contains the upcoming AvaIre release.

If you are unsure if your feature qualifies as a major or minor, please ask Alexis Tan (Senither) in the [AvaIre Central](https://avairebot.com/support) Discord server.

<a name="coding-style"></a>
## Coding Style

AvaIre follows a mix of the [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) coding standard and some custom coding styles, `xo` is used to enforce these rules, you can check if the code you've written follows the coding styles by running `xo` in the command line, running the tests will also test the code for code style breakage.

    npm test

<a name="esdoc"></a>
### ESDoc

Below is an example of a valid AvaIre documentation block. Note that the `@param` attribute is followed by two spaces, the argument type, followed by enough spaces to align the variable name with each other, followed by enough spaces to align the param description with each other.

```javascript
/**
 * Executes the given command.
 *
 * @param  {IUser}     sender   The user object that ran the command.
 * @param  {IMessage}  message  The Discordie message object.
 * @param  {Array}     args     The command arguments.
 * @return {mixed}
 */
onCommand(sender, message, args) {
{
    //
}
```
