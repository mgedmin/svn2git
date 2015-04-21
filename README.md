svn-all-fast-export
===================

This is a fork of https://gitorious.org/svn2git/svn2git/ with a patch that
fixes a segfault.  Quoting the [original
bug](https://gitorious.org/svn2git/svn2git/merge_requests/23):

> Sometimes some revisions are filtered out by authz rules on the server, and
> when you create a mirror with svnsync, you end up with an empty revision that
> has no revprops whatsoever. This means svnlog, svndate and svnauthor are all
> NULL. This used to cause segfaults.
>
> Here's some context: http://svn.haxx.se/users/archive-2013-02/0160.shtml

> I tested this on a mirror of svn.zope.org (which is publically available).
> svn-all-fast-export version 1.0.5 (it calls itself
> 149d6c6e14a1724c96999328683a9264fc508264) segfaults on r129027; this patch
> fixes the segfault.
>
> I only just now noticed that
> https://gitorious.org/svn2git/svn2git/merge_requests/19 appears to be fixing
> the same bug in almost the same way.

Upstream seemed to be dead: they never reacted to my merge request (or to the
older one I missed initially).

Since Gitorious is dying too (GitLab bought it), and since GitLab didn't bother
making a shiny simple "Move to GitLab" buttom so I have to do this by hand, I'm
pushing this to GitHub.

Hey, I found https://github.com/svn-all-fast-export/svn2git on GitHub, which
seems to be the same codebase, so I'll try merging the two.

**UPDATE**: they [merged](https://github.com/svn-all-fast-export/svn2git/pull/1) my pull request yay!


Building
--------

Run ``qmake && make``.  You get ``./svn-all-fast-export``.
