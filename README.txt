Vinculum consists of several modules which implement sending and receiving
messages between websites, including classically formed Trackback, as well
Pingback and Webmention formats. Can provide classic & new blog style pings.

Vinculum base module also makes options available in Views to show activity.

INSTALL

Enable Vinculum and Vinculum UI.
drush: drush en vinculum vinculum_ui

At least one module implementing a
Vinculum handler must be activated i.e.
drush: drush en vinculum_trackback

CONFIGURE

Permissions: there are a couple created for controlling the module and settings.

Menu: Configuration > Content authoring > Vinculum
you can set here if Vinculum will try to scan incoming pings

Individual content type: allow or deny.

Toggle vinculum or refback in the node's settings tabs.

DEVELOPER INFO

Vinculum also has several hooks so it can fit into various workflows, a
custom HTTP getter; the module can scan remote sites to see if links exist.

ISSUES

This module is in early development and 7.x-2.x is not yet alpha release.
Issue queue: https://www.drupal.org/project/issues/vinculum

API reference

vinculum.module includes these public functions:
vinculum_views_api
vinculum_entity_info
vinculum_node_load($nodes, $types) Implements hook_node_load().
vinculum_node_presave($node) Implements hook_node_presave().
vinculum_node_insert($node)
vinculum_node_update($node)
vinculum_vinculum_get_external_links($node)
- Implements hook_vinculum_get_external_links().
vinculum_vinculum_link_send_alter(&$links, $node)
- Implements hook_vinculum_link_send_alter().
vinculum_vinculum_received_validate(VinculumReceived $vinculum)
- Implements hook_vinculum_received_validate().
vinculum_vinculum_received_presave(VinculumReceived $vinculum)
- Implements hook_vinculum_received_presave().
vinculum_rules_vinculum_received_insert(VinculumReceived $vinculum)
vinculum_receive(vinculum $vinculum)
vinculum_receive_validate(vinculum $vinculum)
vinculum_node_allows_vinculum($node, $op)
- Check if a node allows vinculum operations.
vinculum_get_external_links($node)
- Get a list of external links from a node.
vinculum_send_refbacks($links, $node)
- Invoke vinculum handlers on each external link to record a vinculum.
vinculum_send_single_vinculum
- Invoke vinculum handlers to send a vinculum.
vinculum_lookup_nid($url)
- Fetch the node nid from a local URL.
vinculum_is_received($nid, $url)
vinculum_is_sent($nid, $url)
vinculum_get_handler($handler = NULL)
vinculum_load_all_handlers($reset_cache = FALSE)
vinculum_set_weights($weights)
vinculum_drupal_http_request($url, array $options = array())
- straight copy of Drupal Core drupal_http_request() function with
  support for multi value link headers



TECHNICAL REFERENCES
--

Pingback specification
- http://www.hixie.ch/specs/pingback/pingback

Trackback specification
- http://www.sixapart.com/pronet/docs/trackback_spec
- http://archive.cweiske.de/trackback/trackback-1.2.html

Webmention specification
- http://webmention.org
More developer info
- http://indiewebcamp.com/Webmention

Parser.php library for JSON microformat conversion from indieweb
via https://github.com/indieweb/php-mf2
License CC0
https://github.com/indieweb/php-mf2/blob/master/LICENSE.md