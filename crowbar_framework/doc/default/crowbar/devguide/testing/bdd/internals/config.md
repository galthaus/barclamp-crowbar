#### BDD Config

The BDD configuration file contains information that tells BDD how to execute.  While BDD adds to this file during execution, users choose which values it starts with.

BDD selects the `default.config` file automatically.  You can choose which configuration to load by passing it into the `bdd:test(config)` or `bdd:feature(config, feature)` methods.

<table>
  <tr>
    <th>Item</th>
    <th>Required</th>
    <th>Default</th>
    <th>Comment</th>
  </tr>
  <tr>
    <td>URL</td>
    <td>Yes</td>
    <td>none</td>
    <td>This is the URL that BDD will use for testing</td>
  </tr>
  <tr>
    <td>user</td>
    <td>no</td>
    <td>none</td>
    <td>If your site requires auth, then this is required</td>
  </tr>
  <tr>
    <td>password</td>
    <td>no</td>
    <td>none</td>
    <td>If your site requires auth, then this is required.  WARNING: Retained in clear text!  Do not store production passwords here!</td>
  </tr>
  <tr>
    <td>log</td>
    <td>no</td>
    <td>[puts, warn]</td>
    <td>used by bdd_utils:log printouts.  Create list with none, some or all of the following: [puts, trace, debug, info, warn]</td>
  </tr>
</table>

##### Example Config

    %%-*-erlang-*- 
    {url, "http://192.168.124.10:3000"}.
    {user, "developer"}.
    {password,"Cr0wbar!"}.
    {feature_path,"features/"}.
    {extension, "feature"}.
    {global_setup, crowbar}.
    {secondary_step_files, [crowbar_rest, crowbar, bdd_webrat, bdd_restrat, bdd_catchall]}.
    {translation_error, "translation_missing"}.