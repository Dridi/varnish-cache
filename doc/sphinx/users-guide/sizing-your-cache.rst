..
	Copyright (c) 2012-2015 Varnish Software AS
	SPDX-License-Identifier: BSD-2-Clause
	See LICENSE file for full text of license


Sizing your cache
-----------------

Deciding on cache size can be a tricky task. A few things to consider:

 * How big is your *hot* data set. For a portal or news site that
   would be the size of the front page with all the stuff on it, and
   the size of all the pages and objects linked from the first page.

 * How expensive is it to generate an object? Sometimes it makes sense
   to only cache images a little while or not to cache them at all if
   they are cheap to serve from the backend and you have a limited
   amount of memory.

 * Watch the `n_lru_nuked` counter with :ref:`varnishstat(1)` or some
   other tool. If you have a lot of LRU activity then your cache is
   evicting objects due to space constraints and you should consider
   increasing the size of the cache.

Also, there are additional considerations for specific storage engines
(stevedores), see :ref:`guide-storage` for details.
