[![Cpan license](https://img.shields.io/cpan/l/Role-Cache-LRU.svg)](https://metacpan.org/release/Role-Cache-LRU)
[![Cpan version](https://img.shields.io/cpan/v/Role-Cache-LRU.svg)](https://metacpan.org/release/Role-Cache-LRU)

# NAME

Role::Cache::LRU - LRU caching role for Moo class.

# SYNOPSIS

    package MyPackage;

    use Moo;
    with 'Role::Cache::LRU';

    my $mp = MyPackage->new;
    $mp->set_cache('foo', {bar => 1});
    $mp->get_cache('foo');

# DESCRIPTION

Role::Cache::LRU is a Moo's role that provides LRU caching based on
[Cache::LRU](https://metacpan.org/pod/Cache::LRU).

# DEVELOPMENT

Source repository at [https://github.com/kianmeng/role-cache-lru](https://github.com/kianmeng/role-cache-lru).

How to contribute? Follow through the [CONTRIBUTING.md](https://github.com/kianmeng/role-cache-lru/blob/master/CONTRIBUTING.md) document to setup your development environment.

# METHODS

## set\_cache($key, $item)

Add a cache item to the cache. The $key must be a string.

    my $mp = MyPackage->new;
    $mp->set_cache('foo', {bar => 1});
    $mp->set_cache('bar', [1, 2, 3]);

## get\_cache($key)

Get a cached item based on the $key. If nothing is found, returns undef.

    my $mp = MyPackage->new;
    my $item = $mp->get_cache('fishball');
    print $item; # undef

## set\_cache\_size($max)

Set the maximum cached size. The $max value must be larger or equal to 1.
Adjust this to your available maximum memory in your script.

    my $mp = MyPackage->new;
    $mp->set_cache_size(4096);

## get\_cache\_size()

Get the maximum cache size. The default maximum value is 1024.

    my $mp = MyPackage->new;
    print $mp->get_cache_size();
    # 1024

# AUTHOR

Kian Meng, Ang <kianmeng@cpan.org>

# COPYRIGHT AND LICENSE

This software is Copyright (c) 2019 Kian Meng, Ang.

This is free software, licensed under:

    The Artistic License 2.0 (GPL Compatible)

# SEE ALSO

[Cache::LRU](https://metacpan.org/pod/Cache::LRU)
