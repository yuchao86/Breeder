一个简单实用的，可访问zookeeper的C++标准API接口及各种访问操作工具

zookeeper's c++ api and access tool:zk_create, zk_get, zk_update, zk_list, zk_delete, zk_get_acl, zk_set_acl

//===============================================================
zk_create:  create zookeeper node.
./zk_create  -H host:port -n node [-d data] [-f data file] [-o output file] [-a usr:passwd] [-l privilege]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-d: value for node.
-f: data's file. -d is used if it exists
-a: auth user's user:passwd. it can be multi.
-l: node's acl. it can be multi. it's value can be:
    all               :  any privilege for any user;
    self              : any privilege for creator;
    read              : read for any user;
    user:passwd:acrwd : digest auth for [user] with [passwd],
          admin(a), create(c), read(r), write(w), delete(d)
-o: output file, default is stdout
-e: node is EPHEMERAL node
-s: node is SEQUENCE node
-r: recursive to create child.
-h: help

================================================================
zk_get:  get zookeeper node data.
./zk_get  -H host:port -n node [-a usr:passwd] [-o output file]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-a: auth user's user:passwd. it can be multi.
-o: output file, default is stdout
-h: help

================================================================
zk_update:  update zookeeper node.
./zk_update  -H host:port -n node [-d data] [-f data file] [-o output file] [-a usr:passwd] [-v version]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-d: value for node.
-f: data's file. -d is used if it exists
-a: auth user's user:passwd. it can be multi.
-o: output file, default is stdout
-v: node's version
-h: help


===============================================================
zk_list:  get zookeeper node's child.
./zk_list  -H host:port -n node [-a usr:passwd] [-o output file]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-a: auth user's user:passwd. it can be multi.
-o: output file, default is stdout
-h: help

===============================================================
zk_delete:  delete zookeeper node.
./zk_delete  -H host:port -n node [-a usr:passwd] [-v verion] [-o output file] [-r]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-a: auth user's user:passwd. it can be multi.
-v: node's version
-o: output file, default is stdout
-r: recursive to delete child.
-h: help

================================================================
zk_loopcreate:  create zookeeper node for loop.
zk_loopcreate  -H host:port -n node [-d data] [-f data file] [-o output file] [-a usr:passwd] [-l privilege] [-N num]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-d: value for node.
-f: data's file. -d is used if it exists
-a: auth user's user:passwd. it can be multi.
-l: node's acl. it can be multi. it's value can be:
    all               :  any privilege for any user;
    self              : any privilege for creator;
    read              : read for any user;
    user:passwd:acrwd : digest auth for [user] with [passwd],
          admin(a), create(c), read(r), write(w), delete(d)
-o: output file, default is stdout
-e: node is EPHEMERAL node
-s: node is SEQUENCE node
-N: number to create
-h: help

================================================================
zk_get_acl:  get zookeeper node's ACL.
zk_get_acl  -H host:port -n node [-o output file] [-a usr:passwd]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-a: auth user's user:passwd. it can be multi.
-o: output file, default is stdout
-h: help

===============================================================
zk_set_acl:  set zookeeper node's ACL.
./zk_set_acl  -H host:port -n node [-o output file] [-a usr:passwd] [-l privilege] [-v version]
-H: zookeeper's host:port
-n: node name to create, it's full path.
-a: auth user's user:passwd. it can be multi.
-l: node's acl. it can be multi. it's value can be:
    all               :  any privilege for any user;
    self              : any privilege for creator;
    read              : read for any user;
    digest:user:passwd:acrwd : digest auth for [user] with [passwd],
          admin(a), create(c), read(r), write(w), delete(d)
    ip:ip_addr[/bits]:acrwd : ip auth for ip or ip subnet
-m: set Acl mode. [append]°¢[set]°¢[remove] can be set°£default is append.
-o: output file, default is stdout
-r: recursive to set child acl.
-v: node's version
-h: help

===============================================================
zk_lock:  Test for lock zookeeper node.
./zk_lock  -H host:port -n node [-d data] [-f data file] [-o output file] [-a usr:passwd] [-l privilege]

-H: zookeeper's host:port

-n: node name for lock.

-p: prex for lock. default is [lock].

-a: auth user's user:passwd. it can be multi.

-l: node's acl. it can be multi. it's value can be:

    all               :  any privilege for any user;

    self              : any privilege for creator; 

    read              : read for any user;

    user:passwd:acrwd : digest auth for [user] with [passwd], 

          admin(a), create(c), read(r), write(w), delete(d)

-m: watch master node

-h: help
